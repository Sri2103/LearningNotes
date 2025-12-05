# 🧠 DSA PLAYBOOK — 12 CORE PATTERNS

## 🔵 Trigger Checklist

- substring → sliding window
- sorted → two pointers / binary search
- prefix sum → hashmap
- next greater → monotonic stack
- shortest path → BFS
- tree traversal → DFS
- combinations/permutations → backtracking
- optimal → DP
- kth → heap
- connectivity → union-find

---

## 1. Sliding Window

### When to Use

- longest/shortest subarray
- at most k
- frequency restrictions

## Template

```python
l=0
for r in range(n):
    add(nums[r])
    while invalid:
        remove(nums[l]); l+=1
    update result
```

## Key Insight

Expand → Break → Shrink.

---

## 2. Two Pointers

Works for sorted arrays and pair problems.

---

## 3. Prefix Sum + Hashmap

Used for subarray sum = k, prefix difference.

---

## 4. Binary Search

Use for sorted or "search on answer".

---

## 5. Monotonic Stack

Next greater element, intervals.

---

## 6. BFS / DFS

Graphs, trees, components, levels.

---

## 7. Backtracking

Subsets, permutations, combinations.

---

## 8. DP 1D

State transitions on linear structures.

---

## 9. DP 2D

Grid DP, edit distance, knapsack.

---

## 10. Greedy

Sort → pick best local.

---

## 11. Heap

Top-K, merging sorted data.

---

## 12. Union Find

Connectivity, cycle detection.
