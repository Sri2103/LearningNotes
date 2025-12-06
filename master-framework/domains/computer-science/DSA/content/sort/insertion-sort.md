# Insertion sort

## Def

Insertion sort is a simple, in-place comparison-based sorting algorithm that builds a sorted array one element at a time by iteratively inserting elements from an unsorted portion into their correct position in the sorted portion.

## steps

- The algorithm starts with the first element considered sorted.
- For each subsequent element,
  - it compares it with elements in the sorted portion from right to left, shifting larger elements rightward to create space, then inserts the element.
- This mimics sorting playing cards by hand, where you insert each new card into its proper spot

## code implementation

```python
    def insertionSort(arr):
        for i in range(1, len(arr)):
            # take the second element
            key = arr[i]
            # starting up reverse pointer
            j = i-1
            while j >= 0 and key < arr[j]:
                # going in reverse and if current value is less than anything from previous sorted move right
                arr[j+1] = arr[j]
                # decrement j
                j -= 1
            # assign the key to correct spot after moving left
            arr[j+1] = key
```

## Key Features

Modifies the input list directly, using O(1) extra space.

Handles ascending order; change key < arr[j] to key > arr[j] for descending.

Works on any comparable elements, like numbers or strings.​

## Usage Example

- For input [9, 5, 1, 4, 3]
- the function rearranges it to [1, 3, 4, 5, 9] after one call.
- Test with insertionSort(data); print(data) where data = [9, 5, 1, 4, 3].
