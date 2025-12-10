# 🧠 Two-Pointer Master Cheat Sheet (Interview-Ready)

This sheet covers **~90% of all two-pointer problems** by classifying them using:

- Pointer movement style
- Data ordering
- Goal type
- Typical LeetCode examples

---

## ✅ 1. What Is the Two-Pointer Technique?

Two-pointer means:

> ✅ **Using two indices to traverse a structure in a coordinated way to reduce time from O(n²) → O(n).**

Instead of checking all pairs, you:

- Move pointers **intelligently**
- Based on **problem constraints**

---

## ✅ 2. Core Two-Pointer Axes

Every two-pointer problem is defined by:

1. **Pointer Layout**

   - Opposite ends (start & end)
   - Same direction (fast & slow)
   - Two arrays (merge-style)

2. **Data Property**

   - Sorted
   - Unsorted
   - Binary / 0-1
   - String / array

3. **Goal Type**
   - Pair existence
   - Count pairs
   - Remove / compress
   - Partition
   - Maximize / minimize

---

## ✅ 3. Master Two-Pointer Pattern Table

| #   | Pointer Style                 | Data Property        | Core Problem Type         | What You’re Solving          | LeetCode      |
| --- | ----------------------------- | -------------------- | ------------------------- | ---------------------------- | ------------- |
| 1   | Opposite ends (`l,r`)         | **Sorted**           | Pair existence            | Two Sum in sorted array      | 167           |
| 2   | Opposite ends                 | Sorted               | Closest / min diff        | 3Sum Closest                 | 16            |
| 3   | Opposite ends                 | Sorted               | Multiple pair enumeration | 3Sum, 4Sum                   | 15, 18        |
| 4   | Same direction (`slow, fast`) | Unsorted             | Remove in-place           | Remove duplicates / elements | 26, 27        |
| 5   | Same direction                | Unsorted             | Compress in-place         | Remove duplicates II         | 80            |
| 6   | Same direction                | Binary (0/1)         | Partitioning              | Move zeros                   | 283           |
| 7   | Opposite ends                 | Unsorted             | Swapping / reverse        | Reverse string / array       | 344           |
| 8   | Two arrays                    | Sorted               | Merging                   | Merge sorted arrays          | 88            |
| 9   | Fast & slow                   | Linked list          | Cycle detection           | Detect cycle                 | 141           |
| 10  | Fast & slow                   | Linked list          | Middle node               | Find middle                  | 876           |
| 11  | Opposite ends                 | Heights array        | Container optimization    | Max water container          | 11            |
| 12  | Opposite ends                 | Palindrome structure | Symmetry check            | Valid palindrome             | 125           |
| 13  | Same direction                | Window-like          | Maximize distance         | Longest ones with K flips    | 1004 (hybrid) |

---

## ✅ 4. Core Two-Pointer Movement Rules

### ✅ A. Opposite-End Pointers (Sorted / Symmetry Problems)

```python
l = 0
r = n - 1
while l < r:
    if condition:
        l += 1
    else:
        r -= 1
```

| Technique      | Best For                       | Window Size      | Data Structure  |
| -------------- | ------------------------------ | ---------------- | --------------- |
| Two-Pointer    | Pairs, partition, in-place ops | Usually implicit | Often none      |
| Sliding Window | Subarrays / substrings         | Explicit window  | Set, Map, Deque |

🟢 Level 1 — Opposite Ends (Easy)

167, 125, 344

🟡 Level 2 — Fast & Slow (In-place)

26, 27, 283

🟠 Level 3 — Optimization with Opposite Ends

11, 15

🔴 Level 4 — Linked List Fast/Slow

141, 876

## ✅ Two-Pointer Decision Tree (How to Pick the Exact Pattern)

Use this tree in interviews to instantly decide:

- Pointer direction
- Data structure (if any)
- Core invariant

---

```text
START
│
├── Does the problem talk about **PAIRS / TWO VALUES / SYMMETRY**?
│ │
│ ├── YES
│ │ │
│ │ ├── Is the array or input **SORTED**?
│ │ │ → ✅ Opposite-End Two Pointers (l, r)
│ │ │ Examples: 167, 11, 15, 16
│ │ │
│ │ └── Is the string / array about **reversing or palindrome**?
│ │ → ✅ Opposite-End Two Pointers
│ │ Examples: 125, 344
│ │
│ └── NO
│
├── Does the problem require **IN-PLACE MODIFICATION / REMOVAL / COMPRESSION**?
│ │
│ ├── YES
│ │ → ✅ Same-Direction Fast & Slow
│ │ slow = write index
│ │ fast = scan index
│ │ Examples: 26, 27, 80, 283
│ │
│ └── NO
│
├── Does the problem involve a **LINKED LIST**?
│ │
│ ├── Need to detect **cycle**?
│ │ → ✅ Fast & Slow (tortoise–hare)
│ │ Example: 141
│ │
│ ├── Need to find **middle node**?
│ │ → ✅ Fast & Slow
│ │ Example: 876
│ │
│ └── Other linked-list two-runner logic
│ → ✅ Fast & Slow variant
│
├── Does the problem involve **TWO SORTED ARRAYS**?
│ │
│ └── YES
│ → ✅ Merge-Style Two Pointers
│ One pointer per array
│ Example: 88
│
├── Does the problem involve **MAXIMIZING/MINIMIZING a value** with two ends?
│ │
│ └── YES
│ → ✅ Opposite-End Optimization
│ Example: 11 (Container With Most Water)
│
├── Does the problem talk about **K constraint on a subarray/substring**?
│ │
│ └── YES
│ → ❌ This is NOT pure two-pointer
│ → ✅ This is Sliding Window
│ Examples: 3, 76, 219, 239
│
└── Otherwise:
→ Try brute force pair logic
→ If nested loops appear → convert to two-pointer by: - Sorting, or - Using fast/slow compression
```
