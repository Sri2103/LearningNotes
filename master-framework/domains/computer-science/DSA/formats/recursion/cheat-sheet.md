# 🧠 Recursion Master Cheat Sheet (Interview-Ready)

This sheet classifies **~95% of all recursion problems** using:

- Recursion type
- State style
- Branching pattern
- Result type
- Canonical LeetCode examples

---

## ✅ 1. What Is Recursion?

> **Recursion = a function solving a problem by calling itself on smaller versions of the same problem.**

Every recursion has:

1. ✅ **Base Case** → when to STOP
2. ✅ **Recursive Case** → how to REDUCE the problem
3. ✅ **State** → what information is carried forward

---

## ✅ 2. Core Recursion Axes

Every recursion problem is defined by:

1. **Structure**

   - Linear (array/string index)
   - Tree / Graph
   - Decision Tree (combinatorics)
   - Divide & Conquer (ranges)

2. **Goal Type**

   - Existence (True/False)
   - Count
   - Min / Max
   - Generate all solutions

3. **Branching**

   - Single path (1 recursive call)
   - Binary choice (2 calls)
   - Multiple choices (loop + recursion)

4. **State Style**
   - Index-based (`i`)
   - Path-based (`path`)
   - Aggregate-based (`sum`, `depth`, etc.)

---

## ✅ 3. Master Recursion Pattern Table

| #   | Recursion Type    | State Style    | Branching | Core Problem Type       | LeetCode |
| --- | ----------------- | -------------- | --------- | ----------------------- | -------- |
| 1   | Linear recursion  | Index          | 1 path    | Traverse array/string   | 509      |
| 2   | Binary choice     | Index + state  | 2 paths   | Pick / Not pick         | 198      |
| 3   | Backtracking      | Path + choices | Many      | All combinations        | 78, 46   |
| 4   | Combination sum   | Path + sum     | Many      | Target sum combos       | 39       |
| 5   | Tree DFS          | Node           | 2–3       | Tree traversal          | 104, 112 |
| 6   | Divide & Conquer  | (l, r)         | 2         | Split & merge           | 53, 912  |
| 7   | Subset generation | Path           | Many      | Power set               | 78       |
| 8   | Permutations      | Path + used[]  | Many      | Ordering                | 46       |
| 9   | DFS grid          | (r, c)         | 4         | Flood fill / islands    | 200      |
| 10  | DP + recursion    | Memo state     | Many      | Overlapping subproblems | 70, 139  |

---

## ✅ 4. Universal Recursion Frameworks

### ✅ A. Index-Based Recursion (Linear / Binary Choice)

```python
def dfs(i, state):
    # 1️⃣ Base case
    if i == END:
        return RESULT_FROM(state)

    # 2️⃣ Recursive case
    # Option 1: take
    res1 = dfs(i + 1, updated_state1)

    # Option 2: skip (optional)
    res2 = dfs(i + 1, updated_state2)

    # 3️⃣ Combine
    return COMBINE(res1, res2)

```

```python
def backtrack(path, choices):

    # 1️⃣ Base case: valid solution
    if COMPLETE(path):
        result.append(path.copy())
        return

    # 2️⃣ Try all choices
    for choice in choices:
        if not VALID(choice, path):
            continue

        # Choose
        APPLY(choice, path)

        # Recurse
        backtrack(path, choices)

        # Un-choose
        UNDO(choice, path)
```

```python

def dfs(node):
    if node is None:
        return BASE

    left = dfs(node.left)
    right = dfs(node.right)

    return COMBINE(node, left, right)
```

```python
def solve(l, r):
    if l == r:
        return BASE_RESULT

    mid = (l + r) // 2

    left = solve(l, mid)
    right = solve(mid + 1, r)

    return COMBINE(left, right)
```

```python
def dfs(r, c):
    if OUT_OF_BOUNDS or VISITED:
        return

    mark VISITED

    dfs(r+1, c)
    dfs(r-1, c)
    dfs(r, c+1)
    dfs(r, c-1)
```

```code
START
│
├── Does the problem involve a TREE?
│       → ✅ Tree DFS
│
├── Does it ask for ALL combinations / permutations / subsets?
│       → ✅ Backtracking
│
├── Does it split the problem into RANGES?
│       → ✅ Divide & Conquer
│
├── Does it traverse an ARRAY/STRING step-by-step?
│       → ✅ Index-Based Recursion
│
├── Does it explore a GRID?
│       → ✅ Grid DFS
│
├── Does it have OVERLAPPING subproblems?
│       → ✅ Recursion + Memo (DP)
│
└── Otherwise:
        → Try brute recursion → add pruning / memo later
```

✅ 7. Core Recursion Traps

- ❌ Missing base case

- ❌ Not shrinking the problem

- ❌ Forgetting to undo state in backtracking

- ❌ Exponential blow-up without memo

- ❌ Modifying shared state without copying

8. Interview Practice Ladder (Recursion)
   🟢 Level 1 — Linear Recursion

509, 70

🟡 Level 2 — Tree DFS

104, 112

🟠 Level 3 — Backtracking

78, 46, 39

🔴 Level 4 — Divide & Conquer

53, 912

🔵 Level 5 — Grid DFS

200, 733

🟣 Level 6 — Recursion + DP

## 139, 322

One-Line Mental Formula

- Recursion = Define States → Define Base Case → Reduce the Problem → Combine Results
