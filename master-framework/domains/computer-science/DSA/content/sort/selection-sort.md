# selection-sort

Selection sort is an in-place comparison-based sorting algorithm that divides the input list into a sorted sublist and an unsorted sublist. It repeatedly finds the minimum (or maximum) element from the unsorted sublist and swaps it with the first unsorted element, growing the sorted sublist from left to right

## Defintion

## working

The algorithm starts with an empty sorted sublist and the entire list as unsorted. In each pass, it scans the unsorted portion to locate the smallest element and swaps it into position at the boundary. This process repeats until no unsorted elements remain, with passes reducing the unsorted size by one each time

## code implementation

```python
def selection_sort(nums):
    # n is the length of list
    n = len(nums)

    for i in range(n):
        min_index = i

        j = i + 1
        while j < n:
            # check if next element is less than current min
            if nums[j] < nums[min_index]:
                min_index = j
            j += 1

        # swapping
        nums[i],nums[min_index] = nums[min_index], nums[i]


```

## Asymptotic notation

- Time complexity - O(n\*\*2)
- space complexity - O(1)
