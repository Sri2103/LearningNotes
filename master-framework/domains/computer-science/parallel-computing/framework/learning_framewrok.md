# Parallel & Concurrent Programming Learning Framework

## 1. Why am I learning this?

> To write high-performance, correct, scalable programs that utilize multicore CPUs, asynchronous IO, and parallel computing while avoiding race conditions, deadlocks, and performance bottlenecks.

## 2. Subskills (Decomposition)

### Concurrency (Correctness)

- threads, goroutines, coroutines
- synchronization primitives
- mutexes, semaphores
- condition variables
- atomic operations
- message passing (channels, queues)
- deadlocks, livelocks, starvation
- memory models

### Parallelism (Performance)

- SIMD, vectorization
- multicore parallelism
- task scheduling
- work stealing
- CPU cache effects
- false sharing
- GPU parallelism basics

### System Foundations

- OS scheduling
- context switching
- process vs thread
- async IO vs multithreading

### Distributed Concurrency

- distributed locks
- quorum-based coordination
- leader election
- distributed queues

## 3. Knowledge Map

Fundamentals → threads, locks, goroutines  
Intermediate → channels, atomics, perf tuning  
Advanced → lock-free structures, memory models, GPU and distributed concurrency

## 4. Core Resources

Books:

- The Art of Multiprocessor Programming
- Java Concurrency in Practice
- Go Concurrency Patterns
- Operating Systems: Three Easy Pieces

Courses:

- MIT 6.824 (distributed concurrency)
- CMU 15-418 (parallel performance)

## 5. Learning Method

Understand → visualize → model → code → test → break → debug → optimize

## 6. Weekly Practice

- 3 concurrency problems
- 1 parallel algorithm
- 1 race-condition debugging exercise

## 7. Concurrency Playbook

1. Identify shared state
2. Decide lock vs message passing
3. Minimize critical sections
4. Avoid blocking operations
5. Apply atomic operations if needed
6. Validate with race detectors
7. Benchmark

## 8. Parallel Playbook

- partition data
- minimize synchronization
- maximize locality
- use work stealing
- avoid false sharing
- measure speedup

## 9. Common Mistakes

- unnecessary locks
- oversynchronization
- shared mutable state
- not understanding memory model
- goroutine leaks
