# divide and conquer

```python
# Pseudocode framework for divide-and-conquer recursion
def solve(l, r, other_params):
    """
    [l, r] : current range / segment (inclusive or half-open, you decide)
    """

    # 1) Base case: small segment
    if l == r or SMALL_ENOUGH(l, r):
        # Directly compute and return result for this small piece
        ...
        return BASE_RESULT

    # 2) Divide: find mid, split into subproblems
    mid = (l + r) // 2

    left_result = solve(l, mid, other_params)
    right_result = solve(mid + 1, r, other_params)

    # 3) Conquer / combine: merge left_result and right_result
    combined = COMBINE(left_result, right_result, other_params)

    return combined

```
