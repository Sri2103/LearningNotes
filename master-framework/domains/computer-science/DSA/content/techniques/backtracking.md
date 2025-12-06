# Backtracking

## Description

Builds candidates recursively, prunes invalid paths. DFS with undo.

## pseudo code

```text
def backtrack(partial):
    if complete: process()
    for choice:
        if valid: add, recurse, remove

```

## python code

```python
def permute(nums):
    result = []
    def backtrack(path, used):
        if len(path) == len(nums):
            result.append(path[:])
            return
        for i, num in enumerate(nums):
            if not used[i]:
                used[i] = True
                path.append(num)
                backtrack(path, used)
                path.pop()
                used[i] = False
    backtrack([], [False] * len(nums))
    return result

# Test: permute([1,2,3]) -> [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]

```

- Practice: N-Queens, subsets.​

## Resources

[The Ultimate Guide to Backtracking](https://www.abhinavpandey.dev/blog/backtracking-algorithms)
[Backtracking Made Simple](https://algodaily.com/lessons/recursive-backtracking-for-combinatorial-path-finding-and-sudoku-solver-algorithms)
