# sliding window

- A problem-solving method used to optimize problems involving subarrays or substrings.

- Instead of recalculating results for every possible window, you reuse previous computations by sliding the window forward.

- Great for problems involving contiguous sequences (like sums, maximums, or counts).

## Description

Dynamic [left,right] interval, expand/shrink for property.
When to use: Subarray/substring constraints. O(n).

## Key Concepts

- **Window** → A fixed or variable-sized portion of the array/string.

- **Fixed Window** → Window size stays constant (e.g., maximum sum of subarray of size k).

- **Variable Window** → Window size changes based on conditions (e.g., longest substring without repeating characters).

- **Expand** → Move the right pointer to include more elements.

- **Shrink** → Move the left pointer to remove elements when conditions are violated.

- **Reuse Computation** → Instead of recalculating from scratch, update the result by adding/removing elements as the window slides.

## Process Flow

1. Initialize two pointers (left, right) to define the window.

2. Expand the window by moving right.

3. Check condition (sum, uniqueness, length, etc.).

4. If condition breaks, shrink the window by moving left.

5. Keep track of the best result while sliding across the array/string.

## Everyday Example

- Imagine looking through a train window:

- You see a fixed portion of the scenery at a time.

- As the train moves, the window slides forward, showing new scenery while old scenery disappears.

- That’s how the sliding window works in arrays/strings.

## pseudo code

```text
left=0
for right in range(n):
    add right
    while invalid: remove left
    update max

```

## python code

```python
def lengthOfLongestSubstring(s):
    char_set = set()
    left = 0
    max_len = 0
    for right in range(len(s)):
        while s[right] in char_set:
            char_set.remove(s[left])
            left += 1
        char_set.add(s[right])
        max_len = max(max_len, right - left + 1)
    return max_len

# Test: lengthOfLongestSubstring("abcabcbb") -> 3

```

```python

def max_sum_subarray(arr, k):
    window_sum = sum(arr[:k])  # First window
    max_sum = window_sum

    for i in range(k, len(arr)):
        window_sum += arr[i] - arr[i-k]  # Slide window
        max_sum = max(max_sum, window_sum)

    return max_sum

```

```python
def longest_unique_substring(s):
    seen = {}
    left = 0
    max_len = 0

    for right in range(len(s)):
        if s[right] in seen and seen[s[right]] >= left:
            left = seen[s[right]] + 1  # Shrink window
        seen[s[right]] = right
        max_len = max(max_len, right - left + 1)

    return max_len

```

## Where Sliding Window is Used

- Maximum/minimum sum subarray problems.

- Longest substring problems (unique characters, vowels, etc.).

- Counting problems (number of subarrays meeting a condition).

- Streaming data analysis (moving averages).

## Summary

Sliding Window = Reuse results while moving across contiguous sequences.

Two types: Fixed window and Variable window.

Efficient alternative to brute force for subarray/substring problems.

Time complexity often reduced to O(n)
