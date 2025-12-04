# Memory & Storage Playbook

## How to Analyze Any Memory-Related Problem

### 1. Identify Memory Layer

- Register
- L1/L2/L3
- RAM
- Swap
- Disk

### 2. Determine Access Pattern

- Sequential
- Random
- Locality?
- Cache-friendly?

### 3. Determine Allocation Type

- stack
- heap
- mmap

### 4. Evaluate OS involvement

- page faults?
- context switches?
- swapping?

### 5. Check Hardware Constraints

- bandwidth
- latency
- bus speed
- NUMA nodes

---

## Caching Playbook

- Align data to cache lines
- Use locality
- Reduce branching
- Avoid false sharing
- Use SOA (structure-of-arrays) when needed

---

## Virtual Memory Playbook

- Page size = 4KB (commonly)
- Understand page table walk
- Minimize page faults
- Huge pages for large memory workloads

---

## Storage Playbook

- SSD for random IO
- HDD for sequential
- Write amplification awareness
- Use journaling FS for safety
- Use log-structured FS for SSDs

---

## OS Memory Playbook

- Monitor with: `vmstat`, `top`, `/proc/meminfo`
- Understand slab/heap fragmentation
