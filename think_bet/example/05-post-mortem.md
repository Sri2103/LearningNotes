# Postmortem: Add Redis Cache

Decision Date: 2025-03-01
Outcome Date: 2025-03-17

## What Was Expected

Reduced latency with manageable complexity.

## What Actually Happened

Cache invalidation bugs caused stale reads and production incidents.

## Probability Error

Missed Risk

## Root Cause

Overconfidence in cache correctness and rollback safety.

## Signals Missed or Misread

- Low early cache hit rate
- Complexity of invalidation logic

## Lesson Learned

Caching introduces correctness risk, not just performance gains.

## New Rule Added

Never add cache without:

- Proven invalidation strategy
- One-click rollback
