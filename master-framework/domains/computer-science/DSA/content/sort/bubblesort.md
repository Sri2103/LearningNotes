# Bubble sort

Bubble sort is a simple comparison-based sorting algorithm that repeatedly steps through a list, compares adjacent elements, and swaps them if they are in the wrong order.

## Definition

- linear sorting algorithm
- localized swapping trick

## Algorithm

1. start iterating from the start to end over the range of element.
2. create a flag to track if the swapping occurs inside iteration
3. for each iteration compare adjacent elements
   - if the adjacent elements are not in correct order, swap them to form correct order
   - if no swap occurs in the current iteration , it indicates that remeainign iterations have values that are already sorted
4. the array is sorted

## code

```python
def bubble_sort(nums:list[int]):
    n = len(nums)
    for i in range(n-1):
        # doing n-1 rang because , the last base we can sort at max n-1 items out of their position
        swapped = False
        for j in range(0, n-i-1):
            # take at max n-i-1 steps to move largest item to right
            if nums[j] > nums[j+1]:
                nums[j],nums[j+1] = nums[j+1],nums[j]

        if not swapped:
            True

```

## asymptotic notation

space -complexity = O(1)
time-complexity = O(n\*\*2)

## sample iteration

```text
**OUTER i=0** (pass 1): range(5-0-1)=range(4) → 4 comparisons
j=0: [5,4,3,2,1] → swap → [4,5,3,2,1]
j=1: [4,5,3,2,1] → swap → [4,3,5,2,1]
j=2: [4,3,5,2,1] → swap → [4,3,2,5,1]
j=3: [4,3,2,5,1] → swap → [4,3,2,1,5] ← 5 locked at index 4 ✓

**OUTER i=1** (pass 2): range(5-1-1)=range(3) → 3 comparisons (skip index 4)
j=0: [4,3,2,1,5] → swap → [3,4,2,1,5]
j=1: [3,4,2,1,5] → swap → [3,2,4,1,5]
j=2: [3,2,4,1,5] → swap → [3,2,1,4,5] ← 4 locked at index 3 ✓

**OUTER i=2** (pass 3): range(5-2-1)=range(2) → 2 comparisons (skip 3-4)
j=0: [3,2,1,4,5] → swap → [2,3,1,4,5]
j=1: [2,3,1,4,5] → swap → [2,1,3,4,5] ← 3 locked at index 2 ✓

**OUTER i=3** (pass 4): range(5-3-1)=range(1) → 1 comparison (skip 2-4)
j=0: [2,1,3,4,5] → swap → [1,2,3,4,5] ← 2 locked at index 1 ✓
```
