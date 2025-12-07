# Divide and conquer

- A problem-solving strategy that breaks a big problem into smaller subproblems.

- Solve each subproblem individually, then combine their results to solve the original problem.

- Efficient for problems that can be naturally split into parts.

## 🔑 Key Concepts

**Divide** → Split the problem into smaller subproblems.

**Conquer** → Solve each subproblem (often recursively).

**Combine** → Merge the solutions of subproblems to form the final answer.

**Recursion** → Commonly used to implement divide and conquer.

**Base Case** → The smallest version of the problem that can be solved directly.

## process

- Divide the problem into smaller parts.

- Conquer each part (solve recursively).

- Combine the results of the parts.

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

## Where Divide and Conquer is Used

Sorting algorithms → Merge Sort, Quick Sort.

Searching algorithms → Binary Search.

Matrix multiplication → Strassen’s algorithm.

Computational geometry → Closest pair of points.

Dynamic programming optimizations.

- Practice: Quicksort, closest pair.​

## summary

Divide and Conquer = Break → Solve → Combine.

Works well for problems that can be split into independent parts.

Often implemented with recursion.

Time complexity depends on how the problem is divided and combined.
