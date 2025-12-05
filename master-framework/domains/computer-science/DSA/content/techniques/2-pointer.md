# 2 pointer techniques

## Description

Two indices move coordinately on sequence. O(n) post-sort.

- When to use: Sorted arrays, pairs, palindromes.

## pseudo code

```text
i=0, j=n-1
while i<j:
    if cond: adjust

```

## python coe

```python
def two_sum_sorted(nums, target):
    i, j = 0, len(nums) - 1
    while i < j:
        curr = nums[i] + nums[j]
        if curr == target:
            return [i, j]
        elif curr < target:
            i += 1
        else:
            j -= 1
    return []

# Test: two_sum_sorted([2,7,11,15], 9) -> [0,1]

```

Practice: 3Sum, container water.​
