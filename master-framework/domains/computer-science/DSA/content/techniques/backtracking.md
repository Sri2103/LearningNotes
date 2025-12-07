# Backtracking

- A problem-solving technique that tries solutions step by step.

- If a choice doesn’t work, it undoes (backtracks) and tries another.

- Works like trial-and-error with an undo button.

## 🔑 Key Concepts

- **Search Space** → All possible choices or paths.

- **Candidate Solution** → A partial attempt at solving the problem.

- **Decision Point** → A place where you must choose (e.g., left or right in a maze).

- **Constraint Check** → Test if the current choice is valid.

- **Base Case** → Condition that means the problem is solved.

- **Dead End** → A path that cannot lead to a solution.

- **Backtrack (Undo)** → Reverse the last step and try another option.

- **Pruning** → Skip paths early if they obviously won’t work.

- **Branching** → Each choice creates new possible paths.

- **DFS (Depth-First Search)** → Backtracking explores one path fully before trying another.

- **State Space Tree** → A diagram showing all possible choices and paths.

## 🔄 Process Flow

- Try a choice (forward step).

- Check constraints (is it valid?).

- If valid → go deeper (recursive call).

- If invalid → undo (backtrack).

- Repeat until base case (solution found).

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

```python
def solve_maze(maze, x, y, solution):
    n = len(maze)

    # Base Case
    if x == n - 1 and y == n - 1:
        solution[x][y] = 1
        return True

    # Constraint Check
    if x >= 0 and y >= 0 and x < n and y < n and maze[x][y] == 1:
        # Forward Step
        solution[x][y] = 1

        # Recursive Calls
        if solve_maze(maze, x + 1, y, solution):  # Move right
            return True
        if solve_maze(maze, x, y + 1, solution):  # Move down
            return True

        # Dead End → Backtrack
        solution[x][y] = 0
        return False

    return False

```

## Where Backtracking is Used

- Maze solving

- Sudoku solving

- N-Queens problem

- Word search puzzles

- Combinatorial problems (permutations, subsets, etc.)

- Practice: N-Queens, subsets.​

## Resources

[The Ultimate Guide to Backtracking](https://www.abhinavpandey.dev/blog/backtracking-algorithms)
[Backtracking Made Simple](https://algodaily.com/lessons/recursive-backtracking-for-combinatorial-path-finding-and-sudoku-solver-algorithms)
