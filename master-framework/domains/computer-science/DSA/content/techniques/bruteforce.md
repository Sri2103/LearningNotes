# Bruteforce

## Def

Exhaustively tries all possible solutions, guaranteeing correctness but often slow. Ideal for small inputs (n ≤ 20) to establish baseline or generate patterns. When to use: Tiny constraints, permutations/subsets, initial validation. Time: O(2^n) or O(n!).

## pseudocode

```text
for each candidate:
    if valid(candidate):
        update result
```

## python example

```python
def subset_sum(nums, target):
    n = len(nums)
    for mask in range(1 << n):  # 2^n subsets
        sum_val = 0
        for i in range(n):
            if mask & (1 << i):
                sum_val += nums[i]
        if sum_val == target:
            return True
    return False

# Test: subset_sum([3, 34, 4, 12, 5, 2], 9) -> True
```

- **Practice**: Power set, permutations, N-Queens brute.​
