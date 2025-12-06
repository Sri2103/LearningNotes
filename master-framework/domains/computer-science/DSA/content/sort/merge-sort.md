# merge-sort

- divide and conquer

## Ref link

[merge-sort](https://www.hackerearth.com/practice/algorithms/sorting/merge-sort/tutorial/)

## steps

1. divide unsorted list to n sublists, each containing 1 element.
2. Take adjacent pairs of two singleton lists and merge them to form a list of 2 elements.
   N will now convert into
   N/2 lists of size 2.
3. Repeat the process till a single sorted list of obtained.

## implementation

```python
def merge_sort(nums):
    mid = len(nums)//2
    left = merge_sort(nums[:mid])
    right = merge_sort(nums[mid:])

    return merge(left,right)

def merge(left,right):
    # result place holder
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
```

## Key Characteristics

- Time complexity: O(n log n) for all cases (best, average, worst).​

- Space complexity: O(n) due to temporary arrays during merge.​
