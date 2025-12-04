# Distributed Systems Playbook

## Consistency Playbook

- Strong → linearizability
- Causal → happens-before
- Eventual → independent replicas converge

Choose based on:

- read/write ratio
- latency tolerance
- partition tolerance

---

## Failure Detection Playbook

- heartbeats
- timeouts
- suspicion levels
- gossip-based detection

---

## Leader Election Playbook

- Bully algorithm
- Raft election
- Timeouts → candidate → leader

---

## Replication Playbook

- Leader-based
- Leaderless (Dynamo)
- Quorum reads/writes
- Log replication

---

## Distributed Transactions Playbook

- 2PC → blocking
- 3PC → safer but rare
- Saga → microservices-friendly

---

## Clock Playbook

- NTP → approximate sync
- Lamport clocks → ordering
- Vector clocks → causality

---

## Partition Playbook

During network partition:

- Either allow stale reads
- Or deny writes  
  Depending on system goals (CAP).
