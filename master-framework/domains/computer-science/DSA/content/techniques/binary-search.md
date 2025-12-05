# Binary search

## Description

Halves space on monotonic predicate.

When to use: Sorted, find min/max feasible.

## pseudo code

```text
lo, hi = 0, n
while lo < hi:
    mid = (lo+hi)//2
    if check(mid): hi=mid
    else: lo=mid+1

```

## python code

```python
def search_insert(nums, target):
    lo, hi = 0, len(nums)
    while lo < hi:
        mid = (lo + hi) // 2
        if nums[mid] < target:
            lo = mid + 1
        else:
            hi = mid
    return lo

# Test: search_insert([1,3,5,6], 5) -> 2; [1,3,5,6], 2) -> 1

```

- Practice: Peak element, kth smallest.​
