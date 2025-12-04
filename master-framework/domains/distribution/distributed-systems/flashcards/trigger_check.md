# Distributed Systems Trigger Checklist

- Writes slow → leader bottleneck
- Reads stale → eventual consistency in action
- High tail latency → slow follower or GC pause
- Inconsistent data → missing quorum
- Cluster split → network partition
- Sudden failures → heartbeat timeouts
- Reorder events → unsynced clocks
- Duplicate messages → network retry behavior
