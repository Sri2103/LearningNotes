# Arrays

Linear data structure

## Definition

- linear data structure with values stored in contiguous and fixed memroy length

## Deep Explanation

In an array, all the elements or their references are stored in contiguous memory locations. This allows for efficient access and manipulation of elements.

### Terminologies

- **Array element**: element stored in array
- **Array Index**: Elements are accessed by their indexes. Indexes in most of the programming languages start from 0.

### Type of Arrays

- Dynamic array

```python
    # In Python, all types of lists are created same way
    arr = []
```

- Fixed size array

```python
# Create a fixed-size list of length 5,
# initialized with zeros
arr = [0] * 5

# Output the fixed-size list
print(arr)
```

## Type based on dimensions

- **2 dimensional array**: 2-D Multidimensional arrays can be considered as an array of arrays or as a matrix consisting of rows and columns.
- **3 dimensional array**: A 3-D Multidimensional array contains three dimensions, so it can be considered an array of two-dimensional arrays.

## operations of arrays

- Traversal

```python
arr = [1, 2, 3, 4, 5]

print("Linear Traversal: ", end=" ")
for i in arr:
    print(i, end=" ")
print()
```

- Insertion:

```python
# Python program to insert a given element at the beginning
# of an array

arr = [10, 20, 30, 40]
element = 50
print("Array before insertion")
for i in range(len(arr)):
    print(arr[i], end=" ")

# Insert element at the beginning
arr.insert(0, element)

print("\nArray after insertion")
for i in range(len(arr)):
    print(arr[i], end=" ")
```

---

- Deletion:

```python

# Python program to delete an element from the
# beginning of a list using built-in functions

arr = [10, 20, 30, 40]

print("Array before deletion")
for i in range(len(arr)):
    print(arr[i], end=" ")

# Remove the first element
del arr[0]

print("\nArray after deletion")
for i in range(len(arr)):
    print(arr[i], end=" ")
```

---

- Search

```python
arr = [10, 20, 30, 40, 50]
target = 30
found = False

# Linear search using traversal
for i in range(len(arr)):
    if arr[i] == target:
        found = True
        break

if found:
    print("Element found!")
else:
    print("Element not found!")


arr = [10, 20, 30, 40, 50]

# Modifying elements using traversal (increasing each by 5)
for i in range(len(arr)):
    arr[i] += 5

# Print modified array
print("Modified array:", end=' ')
for num in arr:
    print(num, end=' ')
print()
```

- Sorting and search

```python
def binarySearch(arr, x):
    low = 0
    high = len(arr) - 1
    while low <= high:

        mid = low + (high - low) // 2

        # Check if x is present at mid
        if arr[mid] == x:
            return mid

        # If x is greater, ignore left half
        elif arr[mid] < x:
            low = mid + 1

        # If x is smaller, ignore right half
        else:
            high = mid - 1

    # If we reach here, then the element
    # was not present
    return -1

if __name__ == '__main__':
    arr = [2, 3, 4, 10, 40]
    x = 10

    result = binarySearch(arr, x)
    if result != -1:
        print("Element is present at index", result)
    else:
        print("Element is not present in array")
```

---

## Example

Code snippet or diagram.

## Connections

- relates to topic X
- prerequisite for topic Y
