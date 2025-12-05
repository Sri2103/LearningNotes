# greedy algorithm

## Description

Picks locally optimal choice at each step, assuming global optimum. Prove via exchange property.

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
    activities.sort(key=lambda x: x[1])  # sort by end time
    result = [activities[0]]
    last_end = activities[0][1]
    for start, end in activities[1:]:
        if start >= last_end:
            result.append((start, end))
            last_end = end
    return result

# Test: activity_selection([(1,4),(3,5),(0,6),(5,7),(3,9),(5,9),(6,10),(8,11),(8,12),(2,14),(12,16)])
# -> [(1,4), (5,7), (8,11), (12,16)]
```

- **Practice**: Jump game, coin change (canonical).​
