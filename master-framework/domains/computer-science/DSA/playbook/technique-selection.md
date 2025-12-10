# technique selection chart

```text

START
 |
 |-------------------------------------------------------------
 | 1️⃣ BRUTE FORCE CHECK
 |-------------------------------------------------------------
 |-- Can brute force fit within constraints?
 |      YES → Use brute force (iteration or recursion)
 |      NO  ↓
 |
 |-------------------------------------------------------------
 | 2️⃣ ARRAY / STRING QUICK CHECK
 |-------------------------------------------------------------
 |-- Is problem on contiguous subarray/substring?
 |      YES ↓
 |         |-- Window validity monotonic?
 |         |      YES → ⭐ Sliding Window (use two pointers)
 |         |      NO  → Check for split points → Go to D&C
 |      NO  ↓
 |
 |-------------------------------------------------------------
 | 3️⃣ SORTED STRUCTURES CHECK
 |-------------------------------------------------------------
 |-- Is input sorted OR can sorting help?
 |      YES → ⭐ Two Pointers / Binary Search
 |      NO  ↓
 |
 |-------------------------------------------------------------
 | 4️⃣ HASHING / PREFIX POSSIBILITY
 |-------------------------------------------------------------
 |-- Can prefix sums, hashing, frequency maps solve?
 |      YES → ⭐ HashMap / Prefix Sum
 |      NO  ↓
 |
 |-------------------------------------------------------------
 | 5️⃣ BINARY SEARCH POSSIBILITY
 |-------------------------------------------------------------
 |-- Is result monotonic w.r.t. some decision?
 |     (If x works, all >x work OR all <x work)
 |      YES → ⭐ Binary Search on Answer / Index
 |      NO  ↓
 |
 |-------------------------------------------------------------
 | 6️⃣ DIVIDE & CONQUER CHECK
 |-------------------------------------------------------------
 |-- Is there a natural split point?
 |-- Is there a global invalidator element?
 |-- Will splitting produce independent subproblems?
 |       YES → ⭐ Divide & Conquer
 |               - Tool: Recursion
 |               - Optional tool: Stack (iterative D&C)
 |       NO  ↓
 |
 |-------------------------------------------------------------
 | 7️⃣ DYNAMIC PROGRAMMING CHECK
 |-------------------------------------------------------------
 |-- Are subproblems overlapping?
 |-- Does optimal substructure exist?
 |       YES → ⭐ Dynamic Programming
 |               Choose tool:
 |                   - Recursion + Memo (Top-Down)
 |                   - Tables (Bottom-Up)
 |       NO  ↓
 |
 |-------------------------------------------------------------
 | 8️⃣ GRAPH / TREE CHECK
 |-------------------------------------------------------------
 |-- Is input graph-like or tree-like?
 |       YES → ⭐ DFS / BFS
 |               Tools:
 |                   - DFS → Recursion or Stack
 |                   - BFS → Queue
 |       NO  ↓
 |
 |-------------------------------------------------------------
 | 9️⃣ GREEDY POSSIBILITY
 |-------------------------------------------------------------
 |-- Can local best choices guarantee global optimum?
 |       YES → ⭐ Greedy
 |               Tools:
 |                   - Sorting
 |                   - Heap / Priority Queue
 |       NO  ↓
 |
 |-------------------------------------------------------------
 | 🔚 IF ALL FAIL → RE-EVALUATE MODEL OR USE HYBRID
 |-------------------------------------------------------------
END

```
