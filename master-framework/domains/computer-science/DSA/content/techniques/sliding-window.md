# sliding window

## Description

Dynamic [left,right] interval, expand/shrink for property.
When to use: Subarray/substring constraints. O(n).

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
