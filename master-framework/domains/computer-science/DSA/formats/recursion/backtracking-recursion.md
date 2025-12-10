# Backtracking Framework (for “all combinations / paths”)

```python
# Pseudocode framework for backtracking recursion
def backtrack(path, choices, other_params):
    """
    path         : current partial solution (list/string/etc.)
    choices      : remaining available moves / options
    other_params : original input, constraints, etc.
    """

    # 1) Base case: when path is a complete solution
    if COMPLETION_CONDITION(path, other_params):
        # record a copy of path as one valid answer
        results.append(path.copy())
        return

    # 2) Iterate over all choices at this step
    for choice in ITERATE_OVER(choices):

        # 2a) Check if this choice is valid (pruning)
        if not VALID(choice, path, other_params):
            continue

        # 2b) Make the move (choose)
        APPLY(choice, path, choices)  # e.g., path.append(choice), mark used

        # 2c) Recurse
        backtrack(path, choices, other_params)

        # 2d) Undo the move (un-choose, backtrack)
        UNDO(choice, path, choices)  # e.g., path.pop(), unmark used

```
