# System Design Playbook

## Step-by-Step for Any System Design Problem

### 1. Clarify Requirements

- Functional
- Non-functional (latency, SLA, fault tolerance, security)
- Scale (QPS, data size, users)

### 2. Estimate Scale

- Read/Write QPS
- Peak traffic
- Data storage per day
- Total storage after X years

### 3. Design High-Level Architecture

Components:

- Client
- API gateway
- Load balancers
- App servers
- Cache
- DB
- Queue
- Object storage
- CDN

### 4. Dive Into Components

- DB choice (SQL vs NoSQL)
- Schema design
- Partitioning
- Replication
- Cache eviction policy
- Consistency model

### 5. Identify Bottlenecks

- CPU
- Memory
- Disk
- Bandwidth
- Latency

### 6. Reliability & Fault Tolerance

- Redundancy
- Cross-zone deployment
- Health checks
- Failover

### 7. Scaling Strategies

- Vertical scaling
- Horizontal scaling
- Sharding
- Read replicas

### 8. Security Considerations

- Rate limiting
- Identity
- Tokenization
- Encryption

### 9. Tradeoffs

- Performance vs Consistency
- Cost vs Latency
- Complexity vs Reliability

### 10. Final Diagram

- High-level
- Deep-dive per component
