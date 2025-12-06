# quick sort

## definition

Quick sort is based on the divide-and-conquer approach based on the idea of choosing one element as a pivot element and partitioning the array around it such that: Left side of pivot contains all the elements that are less than the pivot element Right side contains all elements greater than the pivot

It reduces the space complexity and removes the use of the auxiliary array that is used in merge sort. Selecting a random pivot in an array results in an improved time complexity in most of the cases.

## steps

1. Choose Pivot:
   - Select an element as pivot (commonly last/first/random element)
2. Partition: - Reorder array so elements < pivot come before it - Elements > pivot come after it
   - Pivot is now in its final sorted position
3. Recurse:
   - Apply quick sort to left sub-array (elements < pivot)
   - Apply quick sort to right sub-array (elements > pivot)

## implementation

[visualizer](https://www.hackerearth.com/practice/algorithms/sorting/quick-sort/visualize/)

![for quick sort](https://he-s3.s3.amazonaws.com/media/uploads/1ea505b.jpg)

```python
# partition function
def partition(arr, low, high):

    # choose the pivot
    pivot = arr[high]

    # index of smaller element and indicates
    # the right position of pivot found so far
    i = low - 1

    # traverse arr[low..high] and move all smaller
    # elements to the left side. Elements from low to
    # i are smaller after every iteration
    for j in range(low, high):
        if arr[j] < pivot:
            i += 1
            swap(arr, i, j)

    # move pivot after smaller elements and
    # return its position
    swap(arr, i + 1, high)
    return i + 1

# swap function
def swap(arr, i, j):
    arr[i], arr[j] = arr[j], arr[i]

# the QuickSort function implementation
def quickSort(arr, low, high):
    if low < high:

        # pi is the partition return index of pivot
        pi = partition(arr, low, high)

        # recursion calls for smaller elements
        # and greater or equals elements
        quickSort(arr, low, pi - 1)
        quickSort(arr, pi + 1, high)

if __name__ == "__main__":
    arr = [10, 7, 8, 9, 1, 5]
    n = len(arr)

    quickSort(arr, 0, n - 1)

    for val in arr:
        print(val, end=" ")
```

## Time complexity

Best Case: O(n log n) (balanced partitions)
Average Case: O(n log n)
Worst Case: O(n²) (unbalanced partitions)

## space complexity

Quick Sort is O(log n) space complexity for the call stack in the average case, but can degrade to O(n) in the worst case with unbalanced partitions. It is generally considered an in-place algorithm as it doesn't require significant additional space.
