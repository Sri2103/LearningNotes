# Databases (SQL + NoSQL + Internals) Learning Framework

## 1. Why am I learning databases?

> To design efficient schemas, optimize queries, understand database internals, and build scalable, reliable data-driven systems.

## 2. Subskills (Decomposition)

- SQL fundamentals
- Query planning & optimization
- Indexing
- Database design
- Transactions & ACID
- NoSQL systems
- Replication & sharding
- Storage engines (B-Tree, LSM tree)
- WAL & MVCC
- Distributed databases
- Caching
- Performance tuning

## 3. Knowledge Map

Fundamentals → SQL, relational modeling  
Intermediate → indexing, joins, transactions  
Advanced → consistency models, distributed systems, storage internals

## 4. Core Resources

Books:

- Designing Data-Intensive Applications
- Database System Concepts
- SQL Anti-Patterns

Courses:

- CMU DB (15-445 / 15-721)
- Stanford Database Systems

## 5. Learning Method

Query → measure → optimize → inspect → redesign

## 6. Practice Plan

Daily: 2 SQL queries  
Weekly: indexing + query optimization  
Monthly: build a database component

## 7. Database Playbook

1. Identify query type (read-heavy, write-heavy)
2. Identify access paths (indexes, scans)
3. Choose storage model (row/column/LSM/B-Tree)
4. Check isolation & consistency
5. Monitor IO, CPU, memory
6. Add caching if needed
7. Scale via replication or sharding

## 8. Common Mistakes

- No indexes
- Incorrect keys
- Over-normalizing
- Under-normalizing
- Inefficient joins
- Ignoring transactions
- No WAL understanding
