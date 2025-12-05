# Dynamic programming

## Description

- Stores subproblem solutions for overlapping + optimal substructure. Memo or tabulate.

- When to use: Paths, knapsack, sequences. Time: O(states \* transitions).

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

- Practice: LIS, LCS, coin change.​
