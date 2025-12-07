# greedy algorithm

- A problem-solving strategy that builds a solution step by step by always choosing the best immediate option (locally optimal choice).

- Assumes that by choosing the best option at each step, you’ll eventually reach the global optimum.

- Simple and efficient, but doesn’t always guarantee the best solution for every problem.

## Local Optimum → The best choice at the current step

- **Global Optimum** → The overall best solution.

- **Greedy Choice Property** → If a problem can be solved by making locally optimal choices that lead to the global optimum.

- **Optimal Substructure** → The problem can be broken down into smaller problems whose solutions combine to form the overall solution.

- **Decision Point** → Each step where a choice is made.

## Process Flow

1. Start with an empty solution.

2. At each step, make the best possible choice (local optimum).

3. Add that choice to the solution.

4. Repeat until the problem is solved or no choices remain.

**When to use**: Scheduling, knapsack fractional, MST intro. Time: Often O(n log n).

## pseudocode

```text

sort by key
while candidates:
    pick best that fits
```

## python example

```python
def activity_selection(activities):
    # activities = [(start, end)]
    activities.sort(key=lambda x: x[1])  # Sort by finish time
    result = []
    last_end = 0

    for start, end in activities:
        if start >= last_end:  # Greedy choice
            result.append((start, end))
            last_end = end

    return result


# Test: activity_selection([(1,4),(3,5),(0,6),(5,7),(3,9),(5,9),(6,10),(8,11),(8,12),(2,14),(12,16)])
# -> [(1,4), (5,7), (8,11), (12,16)]
```

```python
def coin_change(coins, amount):
    coins.sort(reverse=True)  # Sort coins descending
    result = []
    for coin in coins:
        while amount >= coin:
            amount -= coin
            result.append(coin)  # Greedy choice
    return result

# Example: coins = [1, 2, 5, 10, 20, 50], amount = 93
# Output: [50, 20, 20, 2, 1]

```

- **Practice**: Jump game, coin change (canonical).​

## Where Greedy Algorithm is Used

- Minimum Spanning Tree → Kruskal’s and Prim’s algorithms.

- Activity selection / scheduling problems.

- Coin change (with canonical coin systems).

- Huffman coding (data compression).

- Interval scheduling.
