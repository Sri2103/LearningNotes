# Concurrency Trigger Checklist

- Shared mutable state → must protect or remove
- High contention → redesign critical section
- Slow threads → check scheduling, blocking
- Strange bugs → check memory model
- High CPU idle → parallelism missing
- Cache thrashing → false sharing likely
- Long queues → need thread pool tuning
