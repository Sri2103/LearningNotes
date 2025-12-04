# CPU Architecture Playbook

## Instruction Execution Playbook

1. Fetch
2. Decode
3. Execute
4. Memory access
5. Write-back

## Pipelining Playbook

Hazards:

- RAW → stall or forwarding
- WAR
- WAW
- control hazards → branch prediction

Solutions:

- forwarding
- branch predictors
- speculation
- out-of-order execution

## Cache Playbook

- Understand cache levels
- Check associativity
- Understand cache lines
- Identify locality patterns
- Minimize cache misses

## Virtual Memory Playbook

1. Virtual address → page table lookup
2. TLB lookup
3. Physical address or page fault

## Multicore Playbook

- cache coherence (MESI)
- shared vs private caches
- NUMA zones
