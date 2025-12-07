# Bruteforce

- A problem-solving method that tries all possible solutions until the correct one is found.

- It doesn’t use shortcuts or optimizations — just raw trial-and-error.

- Simple to understand and implement, but often inefficient for large inputs.

## 🔑 Key Concepts

- **Exhaustive Search** → Check every possible option.

- **Candidate Solution** → Each possible attempt.

- **Verification** → Test if the candidate meets the condition.

- **Time Complexity** → Usually very high (often O(n²), O(2^n), or worse).

- **Space Complexity** → Depends on how many candidates are stored.

## Process Flow

- Generate all possible solutions.

- For each solution:

- Check if it satisfies the problem’s condition.

- If yes → return solution.

- If no → continue until all options are tried.

## pseudocode

```text
for each candidate:
    if valid(candidate):
        update result
```

## python example

```python
def subset_sum(nums, target):
    n = len(nums)
    for mask in range(1 << n):  # 2^n subsets
        sum_val = 0
        for i in range(n):
            if mask & (1 << i):
                sum_val += nums[i]
        if sum_val == target:
            return True
    return False

# Test: subset_sum([3, 34, 4, 12, 5, 2], 9) -> True


def brute_force_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:  # ✅ Verification
            return i
    return -1  # ❌ Not found


def max_subarray_sum(arr):
    max_sum = float('-inf')
    n = len(arr)

    # 🔄 Exhaustive Search: try all subarrays
    for i in range(n):
        for j in range(i, n):
            current_sum = sum(arr[i:j+1])
            max_sum = max(max_sum, current_sum)

    return max_sum


```

## Where Brute Force is Used

Small input problems where efficiency doesn’t matter.

As a baseline solution before optimizing.

Cryptography (password cracking).

Generating permutations, subsets, or combinations.

- **Practice**: Power set, permutations, N-Queens brute.​
