# Memory & Storage Trigger Checklist

- Slow array iteration → check cache locality
- Increasing latency → possible page faults
- Random IO → SSD needed
- High CPU stalls → memory bottleneck
- Large allocations → use mmap
- Frequent writes → use write buffer or log structuring
- Multithreaded slowdowns → check NUMA
