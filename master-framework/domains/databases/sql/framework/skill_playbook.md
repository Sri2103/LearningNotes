# Database Playbook

## SQL Query Optimization Playbook

1. Inspect EXPLAIN plan
2. Check if index used
3. Identify full table scans
4. Reduce joins
5. Optimize sort/group by
6. Add correct index (B-Tree vs hash)

---

## Indexing Playbook

- B-Tree for ranges
- Hash index for equality
- Composite index for multi-column queries
- Avoid indexing low-cardinality columns

---

## Transaction Playbook

Isolation levels:

- Read Uncommitted
- Read Committed
- Repeatable Read
- Serializable

Use cases:

- banking → serializable
- high throughput → read committed

---

## NoSQL Playbook

Key-value → high throughput  
Document → flexible schema  
Columnar → analytics  
Graph → relationships

---

## Scaling Playbook

- Replication → availability
- Sharding → throughput
- Caching → latency
- Partitioning → parallelization

---

## Storage Engine Playbook

Row-store → OLTP  
Column-store → OLAP  
LSM-tree → write-heavy  
B-Tree → read-heavy
