# Binary search

- A search algorithm used to find an element in a sorted array/list.

- Instead of checking each element one by one, it repeatedly divides the search space in half.

- Much faster than linear search: O(log n) time complexity.

## 🔑 Key Concepts

- **Sorted Array** → Binary search only works if the data is sorted.

- **Low Pointer** → Marks the start of the search range.

- **High Pointer** → Marks the end of the search range.

- **Midpoint** → The middle index between low and high.

- **Comparison** → Check if the target is equal to, less than, or greater than the midpoint value.

- **Halving Search Space** → After each comparison, discard half of the array.

## Process Flow

- Start with low = 0 and high = n-1.

- Find the mid = (low + high) // 2.

- Compare target with arr[mid]:

- If equal → found.

- If target < arr[mid] → search left half (high = mid - 1).

- If target > arr[mid] → search right half (low = mid + 1).

- Repeat until low > high (target not found).

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
def binary_search(arr, target):
    low, high = 0, len(arr) - 1

    while low <= high:
        mid = (low + high) // 2

        if arr[mid] == target:   # ✅ Found
            return mid
        elif arr[mid] < target:  # 🔄 Search right half
            low = mid + 1
        else:                    # 🔄 Search left half
            high = mid - 1

    return -1  # ❌ Not found


# Test: search_insert([1,3,5,6], 5) -> 2; [1,3,5,6], 2) -> 1

```

## ⚡ Where Binary Search is Used

Searching in sorted arrays/lists.

Finding elements in databases or index structures.

Efficient lookups in search engines.

Problems like:

First/last occurrence of an element.

Square root calculation.

Searching in rotated sorted arrays.

- Practice: Peak element, kth smallest.​
