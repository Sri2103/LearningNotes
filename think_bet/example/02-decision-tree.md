# Decision Tree: Add Redis Cache for Read Path

## Decision

Should we add Redis caching to reduce read latency?

## Tree Structure

### Option A: Add Cache

- Outcome 1: Cache performs well
  - Probability: 70%
  - Payoff: +80
- Outcome 2: Cache introduces complexity / bugs
  - Probability: 30%
  - Payoff: -50

EV(Option A) =
(0.70 × 80) + (0.30 × -50)
= 56 - 15
= +41

---

### Option B: Do Nothing

- Outcome 1: Latency manageable
  - Probability: 30%
  - Payoff: +10
- Outcome 2: Latency degrades further
  - Probability: 70%
  - Payoff: -40

EV(Option B) =
(0.30 × 10) + (0.70 × -40)
= 3 - 28
= -25

---

## Notes

- Major risk: stale reads due to inconsistent invalidation
- Secondary risk: increased on-call load
- Reversibility: moderate (rollback exists but not instant)
- Metrics needed: hit rate, p95 latency, error rate
