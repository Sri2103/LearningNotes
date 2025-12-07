# Dynamic programming

- A problem-solving technique used to solve problems by breaking them into smaller overlapping subproblems.

- Instead of solving the same subproblem multiple times, DP stores results and reuses them.

- It’s an optimization over recursion and brute force.

## Key Concepts

Overlapping Subproblems → Same smaller problems appear repeatedly.

Optimal Substructure → The solution to the big problem can be built from solutions to smaller ones.

Memoization (Top-Down) → Store results of recursive calls in a cache (dictionary/array).

Tabulation (Bottom-Up) → Build solutions iteratively using a table/array.

State → Represents the subproblem (e.g., index, sum, position).

Transition → Formula/logic to move from one state to another.

Base Case → Smallest problem solved directly.

## pseudocode

```text
dp[0] = base
for i in 1..n:
    dp[i] = min/max over prev + cost

```

## python code

```python
def knapsack(weights, values, W, n):
    dp = [[0] * (W + 1) for _ in range(n + 1)]
    for i in range(1, n + 1):
        for w in range(1, W + 1):
            if weights[i-1] <= w:
                dp[i][w] = max(values[i-1] + dp[i-1][w - weights[i-1]], dp[i-1][w])
            else:
                dp[i][w] = dp[i-1][w]
    return dp[n][W]

# Test: knapsack([1,3,4,5], [1,4,5,7], 7, 4) -> 9
```

```python
def fib(n, memo={}):
    if n in memo:        # ✅ Already solved
        return memo[n]
    if n <= 1:           # 🏁 Base Case
        return n
    memo[n] = fib(n-1, memo) + fib(n-2, memo)  # 🔄 Recurrence
    return memo[n]

```

```python
def fib(n):
    dp = [0, 1] + [0]*(n-1)  # 📋 Table
    for i in range(2, n+1):
        dp[i] = dp[i-1] + dp[i-2]  # 🔄 Transition
    return dp[n]

```

- Practice: LIS, LCS, coin change.​

## Process Flow

Identify subproblems.

Define the state (parameters that describe the subproblem).

Write the recurrence relation (how current state depends on smaller states).

Choose memoization (top-down recursion + cache) or tabulation (bottom-up table).

Solve base cases and build up to the final solution.

## Where Dynamic Programming is Used

Fibonacci numbers

Climbing stairs / counting ways problems

Knapsack problem

Longest Common Subsequence (LCS)

Matrix chain multiplication

Optimal path problems (shortest path, min cost)

Game theory problems

## Summary

DP = Break → Store → Reuse → Build solution.

Avoids repeated work by caching results.

Two main styles: Memoization (top-down) and Tabulation (bottom-up).

Time complexity usually improves from exponential to polynomial.
