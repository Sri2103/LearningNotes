# Weekly Review — Week of 2025-03-09 → 2025-03-16

## Active Decisions Reviewed

- [x] Add Redis Cache
- [ ] Career Exploration
- [ ] Side Project

## Key Updates

- Cache hit rate significantly lower than expected (45%)
- Stale reads observed → indicates invalidation complexity
- Operational load is increasing for team
- EV dropped from +56 → +20

## Decisions Continued

- None (cache was left in monitoring state)

## Decisions Stopped / Aborted

- Add Redis Cache (EV turned negative on 2025-03-17)

## Calibration Insight

Tendency toward overconfidence in engineering solutions that “look standard.”
Reality: correctness challenges often outweigh performance gains.

## Action for Next Week

Document a checklist for adding caching safely:

- Invalidation pattern
- Rollback readiness
- Observability instrumentation
