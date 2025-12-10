# 🧠 Sliding Window Master Cheat Sheet (Interview-Ready)

This sheet classifies **~95% of all sliding window problems** by:

- Window type
- Data structure
- Question type
- Example LeetCode problems

---

## ✅ 1. Core Sliding Window Axes

Every problem is defined by **three axes**:

1. **Window Behavior**

   - Fixed size (exact `k`)
   - At most `k`
   - Variable (grow + shrink)
   - Chunked (word-based jumps)

2. **Window State (Data Structure)**

   - None (just counters)
   - Set
   - Frequency Map (Counter)
   - Running Sum
   - Deque (monotonic)
   - Bucket / Ordered Set

3. **Question Type**
   - Existence → True / False
   - Count
   - Maximize length / value
   - Minimize length / value
   - All indices

---

## ✅ 2. Master Pattern Table

| #   | Window          | Data Structure      | Problem Type               | LeetCode      |
| --- | --------------- | ------------------- | -------------------------- | ------------- |
| 1   | Variable        | Set                 | Longest unique substring   | 3             |
| 2   | At most k       | Set                 | Duplicate within distance  | 219           |
| 3   | Fixed k         | Running sum         | Max / avg subarray sum     | 643           |
| 4   | Variable        | Running sum         | Smallest subarray ≥ target | 209           |
| 5   | Variable        | Frequency Map       | Minimum valid window       | 76            |
| 6   | Fixed           | Frequency Map       | Anagrams / permutations    | 438, 567      |
| 7   | Fixed (chunked) | Freq Map + Offsets  | Word concatenation         | 30            |
| 8   | At most k       | Freq Map + Counter  | ≤ K distinct / bad items   | 340, 424      |
| 9   | Fixed k         | Monotonic Deque (↓) | Sliding window max         | 239           |
| 10  | Fixed k         | Monotonic Deque (↑) | Sliding window min         | 239 (variant) |
| 11  | At most k       | Bucket Hash / Tree  | Value range duplicate      | 220           |
| 12  | Variable        | Simple counters     | ≤ K zeros / flips          | 1004          |
| 13  | Fixed           | Deque + indices     | First negative in window   | (classic)     |
| 14  | Variable        | Prefix sum + Map    | Subarray sum = k           | 560           |

---

## ✅ 3. Sliding Window Decision Tree

```code
START
│
├── Is window size FIXED?
│ │
│ ├── Need MAX / MIN?
│ │ → Monotonic Deque → (239)
│ │
│ ├── Need duplicates / uniqueness?
│ │ → Set → (219)
│ │
│ ├── Need anagram / freq match?
│ │ → Freq Map → (438, 567)
│ │
│ ├── Need value range (≤ t)?
│ │ → Bucket / Tree → (220)
│ │
│ └── Need sum / average?
│ → Running Sum → (643)
│
└── Window is VARIABLE
│
├── Based on SUM threshold?
│ → Running Sum → (209)
│
├── Based on UNIQUENESS?
│ → Set → (3)
│
├── Based on FREQ MATCH?
│ → Freq Map → (76)
│
├── Based on ≤ K bad items?
│ → Counter → (424, 1004)
│
└── Moves in WORD CHUNKS?
→ Offsets + Freq Map → (30)

```

---

## ✅ 4. Interview Practice Ladder (Correct Order)

### 🟢 Level 1 — Basic Two Pointers (No DS)

- 643, 209

### 🟡 Level 2 — Set Windows

- 3, 219

### 🟠 Level 3 — Frequency Map Windows

- 76, 438, 567

### 🔴 Level 4 — Chunked / Offset Windows

- 30

### 🔵 Level 5 — Monotonic Deque Windows

- 239

### 🟣 Level 6 — Range / Bucket Windows

- 220

---

## ✅ 5. Universal Sliding Window Skeleton

```python
window = ...
left = right = 0

while right < n:
    add(nums[right])    # expand
    right += 1

    while window_invalid:
        remove(nums[left])   # shrink
        left += 1

    update_answer_if_needed()
```
