# Probability Buckets Reference

10% → Very unlikely  
30% → Unlikely  
50% → Toss-up  
70% → Likely  
90% → Very likely

## Rules

- Use buckets unless precise metrics exist
- Never use decimals without explicit justification
- Update directionally first (↑ ↓ ↔)
- When new signals contradict assumptions → shift bucket

## Example Usage (From Redis Cache Decision)

Initial belief:

- Cache success → 70% (Likely)
- Cache failure → 30% (Unlikely)

After early signals:

- Success → 50% (Toss-up)
- Failure → 50% (Toss-up)

After incident:

- Success → 40% (Unlikely)
- Failure → 60% (Likely)
