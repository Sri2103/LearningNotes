# 🧠 Data Structure Selection Cheat Sheet (Sliding Window Focus)

This sheet answers one question:

> “Given the _nature of the constraint_, which **data structure** should I pick?”

---

## ✅ 1. Core Mapping: Purpose → Data Structure

| Purpose / Constraint          | Data Structure         | Why                      |
| ----------------------------- | ---------------------- | ------------------------ |
| **Storing**                   | Array                  | Fast indexed access      |
| **Dynamic growth**            | Linked List            | Cheap insert/delete      |
| **History / backtracking**    | Stack                  | LIFO                     |
| **Maintenance / scheduling**  | Queue                  | FIFO                     |
| **Bidirectional maintenance** | Deque                  | Push/pop both ends       |
| **Instant lookup**            | HashMap / Dict         | O(1) key access          |
| **Uniqueness control**        | Set                    | No duplicates            |
| **Priority control**          | Heap / Priority Queue  | Always get min/max       |
| **Ordered organization**      | Tree (BST/AVL)         | Sorted access            |
| **Prefix search**             | Trie                   | Strings / prefixes       |
| **Connectivity tracking**     | Union-Find             | Components               |
| **Range sum/min/max**         | Segment / Fenwick Tree | Interval queries         |
| **Range normalization**       | Buckets (Hash)         | Value-difference queries |
| **Historical aggregation**    | Prefix Sum             | Past totals              |
| **2D spatial layout**         | Matrix                 | Grids                    |

---

## ✅ 2. Exact Mapping for the Sliding Window Problems You Learned

| LeetCode      | Problem Name                              | Core Constraint                 | Window Type     | Data Structure          | DS Purpose                   |
| ------------- | ----------------------------------------- | ------------------------------- | --------------- | ----------------------- | ---------------------------- |
| **3**         | Longest Substring Without Repeating       | **Uniqueness**                  | Variable        | **Set**                 | Uniqueness control           |
| **219**       | Contains Duplicate II                     | **Exact duplicate ≤ k**         | Fixed ≤ k       | **Set**                 | Existence check              |
| **76**        | Minimum Window Substring                  | **Exact frequency match**       | Variable        | **HashMap / Counter**   | Frequency indexing           |
| **438 / 567** | Find All Anagrams                         | **Exact frequency match**       | Fixed           | **HashMap / Counter**   | Frequency indexing           |
| **30**        | Substring with Concatenation of All Words | **Word-frequency + chunks**     | Fixed (chunked) | **HashMap + Offsets**   | Chunked freq indexing        |
| **239**       | Sliding Window Maximum                    | **Range maximum**               | Fixed k         | **Deque (Monotonic ↓)** | Dominance-pruned maintenance |
| **220**       | Contains Duplicate III                    | **Value range ≤ t & index ≤ k** | Fixed ≤ k       | **Bucket Hash (Dict)**  | Range normalization          |

---

## ✅ 3. How to Choose the DS in 3 Questions (Mental Filter)

Ask these in order:

### 1️⃣ What is the **window rule**?

- Fixed `k`
- At most `k`
- Variable
- Chunked (word length)

### 2️⃣ What is the **constraint**?

- Uniqueness → **Set**
- Frequency / count → **HashMap**
- Max / Min → **Deque**
- Sum / Average → **Running Sum**
- Value difference (≤ t) → **Buckets / Tree**

### 3️⃣ What is the **output type**?

- True / False → Existence
- Length → Maximize / Minimize
- Value → Max / Min
- All indices → Collection output

This directly selects your data structure.

---

## ✅ 4. The “You Started This” Sentence Completion

You started with:

- **Arrays → storing**
- **Queues → maintenance**

Here is the **completed canonical form**:

- **Arrays** → storing
- **Linked Lists** → dynamic linking
- **Stacks** → history & backtracking
- **Queues** → maintenance & scheduling
- **Deques** → bidirectional maintenance
- **HashMaps** → instant lookup
- **Sets** → uniqueness enforcement
- **Heaps** → priority control
- **Trees** → ordered organization
- **Tries** → prefix retrieval
- **Buckets** → range normalization

---

## ✅ 5. Why This Prevents Pattern Memorization

Instead of memorizing:

> “LC-239 uses a deque”

You now think:

> “This is a **range maximum over a moving window** → I need a structure that:
>
> - Evicts from both ends
> - Preserves dominance  
>   → That is a **monotonic deque**.”

This is **first-principle reasoning**, not pattern recall.

---

## ✅ Final One-Line Summary

> **You don’t choose data structures by name — you choose them by the _rule of access the problem enforces_: uniqueness, frequency, order, priority, range, or maintenance.**
