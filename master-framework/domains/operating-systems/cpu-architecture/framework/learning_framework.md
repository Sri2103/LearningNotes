# CPU Architecture Learning Framework

## 1. Why am I learning CPU architecture?

> To understand how computers execute instructions, optimize performance, write efficient code, and build deep systems engineering intuition.

## 2. Subskills (Decomposition)

- CPU components (ALU, CU, registers)
- Instruction cycle
- Assembly & ISA
- Microarchitecture
- Pipelining
- Caches
- Branch prediction
- Memory hierarchy
- Virtual memory (MMU & TLB)
- Multicore & NUMA
- Interrupts
- GPU vs CPU

## 3. Knowledge Map

Fundamentals → CPU components, ISA  
Intermediate → pipelines, caches, MMU  
Advanced → superscalar, OoO execution, branch prediction

## 4. Core Resources

Books:

- Computer Organization and Design – Patterson & Hennessy
- Computer Architecture: A Quantitative Approach
- CSAPP (systems focus)

Courses:

- MIT 6.004
- CMU 15-213

## 5. Learning Method

Diagram → simulate → measure → optimize → reflect

## 6. Practice Plan

Daily: 1 concept + diagram  
Weekly: implement a simulator or pipeline experiment  
Monthly: deep dive into one architecture

## 7. CPU Architecture Playbook

1. Identify architecture level (ISA vs microarchitecture)
2. Identify execution stage (fetch/decode/execute)
3. Identify hazards (RAW, WAR, WAW)
4. Evaluate caching & branching impact
5. Predict performance behavior

## 8. Common Mistakes

- Mixing up ISA and microarchitecture
- Confusing pipeline hazards
- Assuming cache = RAM
- Thinking multi-core = linear speedup
