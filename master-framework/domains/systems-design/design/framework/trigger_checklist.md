# System Design Trigger Checklist

- high QPS → load balancer + horizontal scaling
- low latency → cache + CDN
- large datasets → sharding + partitioning
- async tasks → message queue
- reliability → redundancy + multi-zone
- write-heavy → log-based storage / LSM tree
- read-heavy → cache + read replicas
- global system → CDN + geo-replication
