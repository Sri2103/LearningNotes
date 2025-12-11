# 🧠 RECURSION PLAYBOOK (INTERVIEW-READY, NON-OVERLAPPING VERSION)

A tactical, actionable playbook similar to the Sliding Window Playbook.  
Not a pattern catalog — a **how-to-use recursion** guide.

---

## 1️⃣ WHEN TO USE RECURSION (Trigger Test)

Ask these in order:

1. Does the problem reduce into smaller subproblems?
2. Does the structure itself contain recursion (tree/graph)?
3. Do I need to explore multiple choices?
4. Do I need to generate all combinations/paths?
5. Is a top-down viewpoint more natural than bottom-up DP?

If **YES to any**, recursion is appropriate.

---

## 2️⃣ IDENTIFY THE RECURSION TYPE (Pick ONE)

| Type                             | Trigger                   | Examples                               |
| -------------------------------- | ------------------------- | -------------------------------------- |
| **Backtracking**                 | Need ALL solutions        | Subsets (78), Perms (46), CombSum (39) |
| **Tree DFS**                     | Input is a tree           | Max depth (104), Path Sum (112)        |
| **Index Recursion**              | Move through array/string | Fibonacci (509), House Robber (198)    |
| **Divide & Conquer**             | Split into halves         | Max Subarray (53), Merge Sort (912)    |
| **Memo Recursion (Top-down DP)** | Overlapping subproblems   | Climb stairs (70), Word Break (139)    |
| **Grid DFS**                     | Explore neighbors         | Islands (200), Flood Fill (733)        |

You only need to pick **one** before coding.

---

## 3️⃣ THE CORE QUESTIONS (Same purpose as Invariants in Sliding Window)

Every recursion function MUST answer:

### ✔ Q1: What is my **STATE**?

(index, node, position, sum so far, path so far, etc.)

### ✔ Q2: What is the **BASE CASE**?

(when do I stop?)

### ✔ Q3: How do I **SHRINK / REDUCE** the problem?

(i → i+1, left/right child, smaller segment, fewer choices)

### ✔ Q4: What do I do **BEFORE** recursion?

(append to path, choose an element, mark visited)

### ✔ Q5: What do I do **AFTER** recursion?

(backtrack → undo, unmark, pop)

### ✔ Q6: How do I **COMBINE** results?

(sum, max, OR, append, merge, return boolean)

If these 6 are clear, recursion becomes mechanical.

---

## 4️⃣ UNIVERSAL RECURSION TEMPLATE (Playbook Style)

```python
def recurse(state):
    # 1. BASE CASE
    if FINISHED(state):
        return FINAL_VALUE(state)

    # 2. OPTIONAL: do work entering this level
    ...

    results = []

    # 3. GENERATE NEXT STATES
    for next_state in NEXT_STATES(state):

        # 3a. CHOOSE (backtracking only)
        APPLY(next_state, state)

        # 3b. RECURSE
        ans = recurse(next_state)

        # 3c. COLLECT
        results.append(ans)

        # 3d. UNCHOOSE (backtracking only)
        UNDO(next_state, state)

    # 4. MERGE RESULTS
    return MERGE(results)
```

## 5️⃣ THE RECURSION RULES (like Sliding Window Rules)

- ✔ Rule 1 — State must strictly shrink.

  - No shrink → infinite recursion.

- ✔ Rule 2 — Base case must RETURN a value.

  - No bare return.

- ✔ Rule 3 — In backtracking: must UNDO all mutations.
- ✔ Rule 4 — Use memoization if states repeat.
- ✔ Rule 5 — The recursion body must be pure

(no unsafe global mutations).

## 6️⃣ MENTAL MODEL (The “Sliding Window Intuition” for Recursion)

> Recursion =
> define state → generate next states → recurse → combine outputs.

This is the most important conceptual formula.

## 7️⃣ DEBUGGING PLAYBOOK

Use this checklist in order:

- Infinite recursion → state not shrinking.

- Wrong results → combine step wrong.

- Missing results → missing branches.

- Duplicate results → forgot UNDO.

- TLE → forgot memo.

## 8️⃣ PATTERN ONE-LINERS (Fast recall)

- Subsets: take / skip

- Permutations: choose unused → recurse → unchoose

- Comb Sum: stay + take, OR skip + move

- Tree DFS: solve left, solve right, combine

- Divide & Conquer: split middle, solve halves, merge

- Grid DFS: mark → explore neighbors → return

- Memo: store result before returning

These are the actual “moves” you perform.

## 9️⃣ PRACTICE LADDER (Playbook Version)

🟢 Level 1 — Single Path Recursion

Fibonacci (509)

Sum of array

🟡 Level 2 — Binary Choice

House Robber (198)

Subset-sum variants

🟠 Level 3 — Backtracking

Subsets (78)

Permutations (46)

Combination Sum (39)

🔴 Level 4 — Tree Recursion

Max Depth (104)

Path Sum (112)

🔵 Level 5 — Divide & Conquer

Max Subarray (53)

Sort problems

🟣 Level 6 — Memo Recursion (Top-down DP)

Climb Stairs (70)

Word Break (139)

## 🔟 ONE-LINE FORMULA (Playbook Final)

Recursion = Base Case → Next States → Recurse → Combine.
