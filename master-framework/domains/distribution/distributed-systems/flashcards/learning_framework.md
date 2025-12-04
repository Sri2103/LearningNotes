# Distributed Systems Learning Framework

## 1. Why am I learning distributed systems?

> To build scalable, fault-tolerant systems, design microservices correctly, reason about failures, and architect real-world distributed backends.

## 2. Subskills (Decomposition)

- Distributed communication
- Replication & sharding
- Consistency models
- Leader election
- Consensus algorithms
- Distributed transactions
- Failure detection
- Distributed coordination
- Distributed caching
- Messaging & logs
- Observability in distributed systems

## 3. Knowledge Map

Fundamentals → CAP, replication, consistency  
Intermediate → leader election, sharding, distributed logs  
Advanced → Raft, Paxos, vector clocks, gossip, transaction protocols

## 4. Core Resources

Books:

- Designing Data-Intensive Applications
- Distributed Systems (Tanenbaum)
- Distributed Systems for Fun & Profit

Courses:

- MIT 6.824
- Berkeley CS 162 (OS + dist systems)

## 5. Learning Method

Visualize → simulate → build → fail → fix → refine

## 6. Practice Plan

Daily → small consistency exercises  
Weekly → distributed algorithm simulation  
Monthly → build a distributed component

## 7. Distributed Systems Playbook

1. Identify communication pattern (sync/async)
2. Identify consistency requirements
3. Identify replication mechanism
4. Evaluate partition behavior
5. Choose coordination mechanism
6. Handle failures explicitly
7. Use logs for ordering
8. Validate correctness under concurrency

## 8. Common Mistakes

- Assuming network reliability
- Ignoring partitions
- Forgetting clock drift
- Overusing distributed locks
- Not designing for failure recovery
