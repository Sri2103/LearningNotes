# Parallel & Concurrency Playbook

## Concurrency Problem Playbook

1. Identify shared state
2. Can it be eliminated?
3. If not, choose model:
   - message passing
   - mutex
   - RW lock
   - atomic operations
4. Define critical sections
5. Avoid nested locks
6. Validate with race detection
7. Benchmark for contention

---

## Deadlock Playbook

Deadlock requires:

1. mutual exclusion
2. hold and wait
3. no preemption
4. circular wait

Avoidance:

- lock order
- try-lock
- lock timeout
- break circular dependencies

---

## Goroutine / Thread Playbook

- never leak goroutines
- always cancel with context
- use bounded worker pools
- avoid blocking calls inside goroutines

---

## Parallelism Playbook

1. Partition problem
2. Minimize cross-thread communication
3. Align memory to avoid false sharing
4. Use parallel-friendly data structures
5. Use SIMD when possible
6. Benchmark using real workloads

---

## Distributed Concurrency Playbook

- don’t rely on global locks
- use leader election
- use quorum-based consistency
- avoid clock-based correctness
