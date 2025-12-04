# CPU Architecture Trigger Checklist

- Slow loop → check cache locality
- Branch-heavy code → branch predictor misses
- Large memory usage → TLB pressure
- Multithreading slowdown → NUMA or lock contention
- Random latency spikes → pipeline stalls
