# Database Trigger Checklist

- Slow queries → missing index
- High CPU → sorting or hash joins
- High IO → full table scans
- Stale reads → replication lag
- Write conflicts → lock contention
- Hot partition → bad sharding key
- High latency → WAL or disk bottleneck
