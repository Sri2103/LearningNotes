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

## 🧠 Technique Selection Flowchart — Full Walkthrough (Using LeetCode 395)

## 🎯 Goal

To learn how to **systematically select the correct problem-solving technique** using a real example and a strict decision flow.

Problem Used:

- **Longest Substring with At Least K Repeating Characters**
- LeetCode 395

---

## ✅ Step 1: Brute Force Check

**Question:**
Can we try all substrings and verify each one?

- Number of substrings = O(n²)
- Checking frequency per substring = O(n)
- Total = **O(n³)** (Too slow for n up to 10⁴)

**Decision:** ❌ Brute force rejected

---

## ✅ Step 2: Sliding Window Check (Substring Test)

**Question:**
Is this a contiguous substring problem?

✔ Yes → Try Sliding Window

Now test sliding window validity:

Sliding Window works only when:

- Expanding window increases validity predictably
- Shrinking window repairs violations locally

But in this problem:

- Validity depends on **global character frequency ≥ k**
- Shrinking window cannot fix the issue if a character is globally invalid
- Violations are **not locally repairable**

**Decision:** ❌ Sliding Window rejected  
➡️ Escalate to higher technique

---

## ✅ Step 3: Sorted Structure / Two Pointers Check

**Question:**
Is input sorted or does sorting help?

- Sorting destroys substring continuity
- No meaningful order-based pairing logic

**Decision:** ❌ Two pointers / sorting rejected

---

## ✅ Step 4: Hashing / Prefix Sum Check

**Question:**
Can frequency maps or prefix sums alone solve it?

- Frequency map can detect character counts
- But cannot enforce **“each character ≥ k times”** for substrings efficiently

**Decision:** ❌ Hashing alone insufficient

---

## ✅ Step 5: Binary Search on Answer Check

**Question:**
Is the answer monotonic?

- If length L works, does L+1 always work? → ❌ No
- Substring validity depends on content, not just length

**Decision:** ❌ Binary Search rejected

---

## ⭐ Step 6: Divide & Conquer Check (Critical Step)

**Key Question:**
Is there a **global invalidator** that breaks all valid substrings crossing it?

Yes.

Example:
If a character appears **less than k times in the entire string**,  
then **NO valid substring can include that character**.

So that character becomes a **natural split point**.

This guarantees:

- Natural splitting ✅
- Independent left/right subproblems ✅
- Same problem structure after split ✅
- Easy combine step using `max()` ✅

**Decision:** ✅ **Divide & Conquer SELECTED**

- Strategy: Split at globally invalid characters
- Tool: **Recursion**

---

## ✅ Step 7: Dynamic Programming Check

DP is only required when:

- Subproblems **overlap**
- Results must be reused

But Divide & Conquer here produces:

- **Independent subproblems**
- No overlap

**Decision:** ❌ DP not needed

---

## 🏁 Final Technique Selection

| Layer    | Selected              |
| -------- | --------------------- |
| Strategy | ✅ Divide & Conquer   |
| Tool     | ✅ Recursion          |
| Combine  | ✅ `max(left, right)` |

---

## 🧠 Final Reasoning Summary

| Technique           | Why It Failed                    |
| ------------------- | -------------------------------- |
| Brute Force         | O(n³) too slow                   |
| Sliding Window      | Violations are global, not local |
| Two Pointers        | No sortable structure            |
| Hashing             | Cannot enforce ≥k condition      |
| Binary Search       | No monotonic property            |
| ✅ Divide & Conquer | Perfect global splitter exists   |
| DP                  | Subproblems are independent      |

---

## ✅ Final Law Learned

> If a **global invalid element exists that no valid answer can cross**,  
> ❗ Sliding Window fails →  
> ✅ **Divide & Conquer becomes the correct technique.**

---

## ✅ Implementation Mapping

- **Technique:** Divide & Conquer
- **Tool:** Recursion
- **Reason:** Natural split by globally invalid characters
- **Combine Step:** `max(left_result, right_result)`

---

## 🎯 Interview Execution Summary

1. Try brute force ❌
2. Try sliding window ❌
3. Reject sorted & hashing methods ❌
4. Test binary search ❌
5. Detect global splitter ✅
6. Apply Divide & Conquer ✅
7. Use recursion to implement ✅
