# Operating Systems Playbook

## When analyzing an OS problem

### 1. Identify subsystem

- CPU
- Memory
- Storage
- Process
- Sync
- IO

### 2. Identify mechanism

- scheduling
- paging
- locking
- interrupt
- DMA
- caching

### 3. Identify algorithm

- FIFO, LRU, MFU
- Round Robin
- MLFQ
- Buddy allocator
- Deadline scheduler

### Process Debug Playbook

- Check process state (running, blocked)
- Check system calls
- Check CPU scheduling history

### Memory Debug Playbook

- Check page faults
- Check TLB misses
- Check swapping activity

### Filesystem Playbook

- Understand block layout
- Understand journaling
- Understand inode

### Synchronization Playbook

- Identify critical sections
- Avoid deadlocks
- Use correct locking primitive
