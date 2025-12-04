# Memory & Storage Learning Framework

## 1. Why am I learning this?

> To deeply understand how computers work internally, optimize performance, reason about memory, and design efficient systems.

## 2. Subskills (Decomposition)

- CPU architecture
- Registers, cache hierarchy
- RAM internals
- Virtual memory & paging
- Memory allocation
- Storage systems
- SSD/HDD internals
- Filesystems
- Memory-mapped I/O
- DMA
- OS memory management

## 3. Knowledge Map

Fundamentals → bits/bytes, CPU, RAM  
Intermediate → caching, paging, locality  
Advanced → SSD firmware, filesystem internals, NUMA

## 4. Core Resources

Books:

- Computer Systems: A Programmer's Perspective (CSAPP)
- Operating Systems: Three Easy Pieces (OSTEP)
- Modern Operating Systems – Tanenbaum

Courses:

- CMU 15-213
- MIT 6.S081

## 5. Learning Method

Read → Model → Test → Explore → Debug → Document

## 6. Practice Plan

Daily: concepts + small experiments  
Weekly: OS-level projects  
Monthly: deep dive into one subsystem

## 7. Memory Playbook

1. Identify memory level (L1, L2, RAM, disk)
2. Estimate latency
3. Consider locality (spatial/temporal)
4. Identify allocation type (stack/heap/mmap)
5. Evaluate OS involvement
6. Predict performance impact

## 8. Common Mistakes

- Thinking memory is “flat”
- Confusing address spaces
- Ignoring cache alignment
- Misunderstanding virtual memory
- Assuming SSD = instantaneous
