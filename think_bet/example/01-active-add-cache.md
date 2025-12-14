# Decision: Add Redis Cache to Read Path

Status: Active
Start Date: 2025-03-01
Owner: Harsha
Time Horizon: 3 months

## Problem Statement

Should we add a Redis cache to reduce API latency for read-heavy endpoints?

## Why This Matters

p95 latency is ~900ms, impacting user experience and SLAs.

## Options

### Option A: Add Redis Cache

Probability: 70%
Payoff: +80
Expected Value: +56
Reasoning:
Caching is a known solution; workload is read-heavy; Redis already approved.

### Option B: Do Nothing

Probability: 30%
Payoff: -40
Expected Value: -12
Reasoning:
Latency issues likely persist; risks customer churn.

## Decision Chosen

Option A — higher EV (+56 vs -12)

## Review Plan

Next Review Date: 2025-03-15
Abort Condition:

- Error rate > 2% for 10 minutes
- Rollback takes more than 5 minutes
