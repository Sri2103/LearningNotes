# Calibration Entry

Decision: Add Redis Cache
Option: Add Cache
Predicted Probability: 70%
Actual Outcome: Failure

## Calibration Result

Overestimated

## Why This Happened

Relied too heavily on prior cache successes without accounting for data consistency complexity.

## Adjustment to Future Priors

Start cache success probability at 50% unless invalidation is trivial.
