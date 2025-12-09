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

## python code

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

## methodologies

- prefix and suffix max (Dynamic programming - can be seen later -lc-31)
- dutchflag problems(where needed 3 partion, left,current,right)(-lc-75)

---

## 2 pointer variants

| Problem Type             | Use This Variant |
| ------------------------ | ---------------- |
| Palindrome / Pair search | Opposite Ends    |
| In-place filtering       | Read–Write       |
| Cycle / Middle           | Fast–Slow        |
| K-th from end            | Gap-Based        |
| Merge at back            | Backward Fill    |
| Pivot grouping           | Partition        |
| Exactly 3 categories     | Dutch Flag       |
| Distance-based duplicate | Implicit Index   |
| Subarray optimization    | Window Hybrid    |
| Compare two arrays       | Dual Arrays      |

## utility in production

- two independent cursors that move with different rules

### Merging sorted array(log systems and dbs)

Used in:

- Merging two sorted log streams

- Database merge joins

- Time-series reconciliation

Example (conceptually):

```text
Pointer A → logs from server 1
Pointer B → logs from server 2
Merge by timestamp
```

### Diff Tools & Synchronization

Used in:

- Git diff

- File synchronization tools

- Document comparison

- rsync-style tools

- Two pointers walk across two files and compare line by line.

### Network Packet Stream Processing

Used in:

TCP stream reassembly

Protocol parsing

Frame decoding

```text
read_ptr → scanning buffer
write_ptr → compacting buffer

```

### Memory Compaction & Garbage Collection

Used in:

- JVM

- Go runtime

- Operating Systems

Two pointers:

- One scans objects

- One compacts live objects

### summary

| Interview Pattern  | Production Name              |
| ------------------ | ---------------------------- |
| Two pointers merge | Stream merge                 |
| Read/Write pointer | Buffer compaction            |
| Fast/Slow pointer  | Cycle & corruption detection |
| Opposite pointers  | Bounds search                |

## pattern recognition

You should immediately think Two Pointers when you see:

- ✅ “sorted array”

- ✅ “pair”

- ✅ “two ends”

- ✅ “remove in-place”

- ✅ “merge”

- ✅ “compare from both sides”

- ✅ “fast & slow”

- ✅ “in-place without extra memory”

### submodels

| Variant       | Mental Image                 |
| ------------- | ---------------------------- |
| Opposite Ends | Two walls closing in         |
| Read & Write  | Scanner + Builder            |
| Fast & Slow   | Runner & Walker              |
| Gap Based     | Two people walking with rope |
| Merge         | Two conveyor belts           |

### pattern structures

#### Opposite ends

```python
l, r = 0, n-1
while l < r:
    if condition:
        l += 1
    else:
        r -= 1

```

#### Read and write

```python
write = 0
for read in range(n):
    if valid(nums[read]):
        nums[write] = nums[read]
        write += 1

```

#### Fast and sloe

```python
write = 0
for read in range(n):
    if valid(nums[read]):
        nums[write] = nums[read]
        write += 1

```
