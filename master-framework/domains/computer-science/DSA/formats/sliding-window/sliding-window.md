# sliding window format

```python
def slidingWindow(data):
    # ✅ WINDOW STATE (choose based on problem)
    # set()        → uniqueness
    # dict()/map   → frequency
    # int          → sum / count
    # deque        → max / min
    window = ...

    left, right = 0, 0

    while right < len(data):

        # =========================
        # 1️⃣ ADD (WRITE PHASE)
        # =========================
        c = data[right]
        window.add(c)       # or window[c] += 1, push to deque, etc.

        # related WRITE updates
        # matched += 1
        # current_sum += c
        # maintain deque monotonicity
        ...

        # =========================
        # 2️⃣ EXPAND
        # =========================
        right += 1

        # =========================
        # 3️⃣ SHRINK (REPAIR PHASE — WRITE ONLY)
        # =========================
        while left < right and window_needs_shrink:

            d = data[left]
            window.remove(d)    # or window[d] -= 1, pop from deque, etc.

            # related WRITE updates
            # matched -= 1
            # current_sum -= d
            ...

            left += 1

        # =========================
        # 4️⃣ READ (OBSERVATION PHASE — NO MUTATION)
        # =========================
        if window_is_valid:
            read_or_store_answer()

```

## The Final Law (This Is What You Lock In)

- All sliding window algorithms must follow:
- ADD → EXPAND → SHRINK (repair invalidity) → READ (observe validity)

- ❌ Never read before expand
- ❌ Never read inside shrink
- ❌ Never mix read logic with mutation logic

## What This Framework Guarantees

| Rule                          | Enforced? |
| ----------------------------- | --------- |
| Add before expand             | ✅        |
| Shrink only after expand      | ✅        |
| Shrink only while invalid     | ✅        |
| Read only after full repair   | ✅        |
| No reading inside shrink      | ✅        |
| No reading before expand      | ✅        |
| No mixed read/write ambiguity | ✅        |

## How Every Sliding Window Problem Plugs In

| Problem | `window`   | `window_needs_shrink` | `window_is_valid` | `read`       |
| ------- | ---------- | --------------------- | ----------------- | ------------ |
| LC-3    | set        | duplicate exists      | always            | update max   |
| LC-219  | set        | size > k              | duplicate found   | return True  |
| LC-220  | bucket map | size > k              | bucket hit        | return True  |
| LC-239  | deque      | size > k              | size == k         | append max   |
| LC-76   | freq map   | extra chars           | all needs met     | update min   |
| LC-30   | word map   | freq exceeded         | matched == k      | append index |
