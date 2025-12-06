# 2 pointer techniques

## Description

Two indices move coordinately on sequence. O(n) post-sort.

- When to use: Sorted arrays, pairs, palindromes.

## pseudo code

```text
i=0, j=n-1
while i<j:
    if cond: adjust

```

## python coe

```python
def two_sum_sorted(nums, target):
    i, j = 0, len(nums) - 1
    while i < j:
        curr = nums[i] + nums[j]
        if curr == target:
            return [i, j]
        elif curr < target:
            i += 1
        else:
            j -= 1
    return []

# Test: two_sum_sorted([2,7,11,15], 9) -> [0,1]

```

Practice: 3Sum, container water.​

## resources

[Dissecting the two pointer technique](https://dev.to/charlesamakoye/dissecting-the-two-pointer-technique-2lb4)

## Technique

### Moving toward

- This approach involves two pointers starting from opposite ends of the data structure and moving toward each other, meaning the pointers move in opposite directions
- This type of two-pointer technique is particularly useful in scenarios where you want to find a pair of elements that meet certain conditions or when comparing elements from both ends.
- Common use cases include checking for a palindrome or finding pairs with a specific sum

- **Approach**

- Initialize the Pointers: Start with one pointer at the beginning (left) and the other at the end (right) of the data structure.
- Move the Pointers: Adjust the pointers towards each other based on the given conditions.
- Check Conditions: Continue moving the pointers toward each other until the desired result is found or a specific condition is met

### Moving Away

- In this approach, both pointers start from the same end of the data structure and move in the same direction.
- This technique is often used when you need to track a window or sub-array within an array, allowing you to efficiently move and adjust the window based on certain conditions.
- Common use cases include the sliding window technique and merging sorted arrays.

- **Approach**

- Initialize Two Pointers: Start with both pointers at the beginning of the data structure.
- Move the Pointers: Move one pointer (usually the faster one) ahead of the other based on specific conditions.
- Adjust the Pointers: Modify the positions of the pointers as needed to maintain the desired window conditions.
