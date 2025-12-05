# Divide and conquer

## Description

Recursively divides into subproblems, solves, merges. T(n) = aT(n/b) + f(n).

- **When to use**: Sorting, searching, matrix ops. Balanced for O(n log n).

## pseudocode

```text
if base: return
left = dac(left)
right = dac(right)
return merge(left, right)

```

## python example

```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    return merge(left, right)

def merge(left, right):
    result = []
    i = j = 0
    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1
    result.extend(left[i:])
    result.extend(right[j:])
    return result

# Test: merge_sort([38,27,43,3,9,82,10]) -> [3,9,10,27,38,43,82]

```

- Practice: Quicksort, closest pair.​
