# 2 pointer techniques

- A problem-solving method where you use two indices (pointers) to scan through data (usually arrays or strings).
- Instead of brute force checking all pairs, you move the two pointers smartly to reduce time complexity.
- Commonly used in problems involving searching, sorting, or optimizing subarrays/substrings.

## 🔑 Key Concepts

**Pointer** → A variable that represents a position in the array/string.

**Left Pointer** (start) → Usually begins at the start of the array.

**Right Pointer** (end) → Usually begins at the end of the array.

**Movement** → Depending on the problem, you move one or both pointers inward or forward.

**Condition Check** → At each step, check if the current pair/segment meets the requirement.

**Shrink/Expand Window** → Sometimes pointers define a "window" (subarray/substring) that grows or shrinks.

**Termination** → Stop when pointers cross each other or when the condition is satisfied.

## 🔄 Process Flow

- Place two pointers at different positions (start/end or both at start).

- Check condition (sum, match, length, etc.).

- Move pointers based on the condition:

- If too small → move right pointer forward.

- If too large → move left pointer forward.

- Repeat until pointers meet or condition is satisfied.

## pseudo code

```text
i=0, j=n-1
while i<j:
    if cond: adjust

```

## python coe

```python
def two_sum(arr, target):
    left, right = 0, len(arr) - 1

    while left < right:
        current_sum = arr[left] + arr[right]

        # ✅ Condition Check
        if current_sum == target:
            return (arr[left], arr[right])

        # 🔄 Move Pointers
        elif current_sum < target:
            left += 1  # move right to increase sum
        else:
            right -= 1  # move left to decrease sum

    return None


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
