# Concurrency Mistake Log

## Common Mistakes I’ve Made

- reading shared data without lock
- writing without atomic operations
- deadlocks caused by lock ordering
- spawning infinite goroutines
- busy-wait loops
- race conditions on counters

## Fix Strategy

- rewrite shared state to message passing
- use context cancellation
- define lock hierarchy
- use WaitGroups carefully
- use tools: go race detector, thread sanitizers
