# two-pointer framework

```python
def twoPointer(data):
    # ✅ Pointers are initialized based on problem type
    left, right = INITIAL_LEFT, INITIAL_RIGHT

    # ✅ Loop condition depends on whether pointers move toward or away
    while LEFT_RIGHT_RELATION:

        # =========================
        # 1️⃣ READ CURRENT STATE (NO MUTATION)
        # =========================
        left_val  = data[left]
        right_val = data[right]

        # =========================
        # 2️⃣ CHECK CONDITION (DECISION PHASE)
        # =========================
        if CONDITION_ON(left_val, right_val):
            handle_result()      # store answer, update best, etc.

        # =========================
        # 3️⃣ MOVE POINTER(S) (MUTATION PHASE)
        # =========================
        if MOVE_LEFT:
            left += 1

        if MOVE_RIGHT:
            right -= 1   # or right += 1 depending on pattern

```

## the 3 laws of 2 pointer

These are the invariants that must never be violated:

- ✅ READ before MOVE

- ✅ DECIDE before MOVE

- ✅ MOVE based only on current comparison

- ❌ Never move both blindly
- ❌ Never move before comparing
- ❌ Never modify data during read

## 3 core invariants

### 1️⃣ Converging Two Pointers (Opposite Ends)

Used for:

- Two Sum (sorted)

- Palindrome

- Container With Most Water

✅ Framework Instantiation:

```python
left, right = 0, len(data) - 1

while left < right:

    if CONDITION(data[left], data[right]):
        handle_answer()

    if need_smaller:
        right -= 1
    else:
        left += 1

```

```text
✅ Key Invariant:
Search space shrinks from both ends
```

### 2️⃣ Same-Direction Two Pointers (Fast & Slow)

Used for:

- Remove duplicates

- Move zeros

- dup sorted array

✅ Framework Instantiation:

```python
slow = 0

for fast in range(len(data)):

    if CONDITION(data[fast]):
        data[slow] = data[fast]
        slow += 1
```

✅ Key Invariant:

```text
slow = last valid position
fast = explorer
```

### 3️⃣ Expanding Two Pointers (Window-Like, No Shrink Loop)

Used for:

- Merge two sorted arrays

- Compare sequences

✅ Framework Instantiation:

```python
i, j = 0, 0

while i < len(A) and j < len(B):

    if A[i] <= B[j]:
        take A[i]
        i += 1
    else:
        take B[j]
        j += 1
```

| Problem                 | Two Pointer Type |
| ----------------------- | ---------------- |
| Two Sum II (Sorted)     | Converging       |
| Remove Duplicates       | Fast-Slow        |
| Move Zeros              | Fast-Slow        |
| Merge Sorted Arrays     | Parallel         |
| Valid Palindrome        | Converging       |
| Squares of Sorted Array | Converging       |
