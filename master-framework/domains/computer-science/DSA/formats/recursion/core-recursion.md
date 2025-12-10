# core recursion (index + state)

```python
# Pseudocode framework for recursion (index-based)
def recur(i, state, other_params):
    """
    i            : current position / step
    state        : current partial result / context (can be passed or global)
    other_params : problem-specific info (nums, target, etc.)
    """

    # 1) Base case: when to STOP
    #    Typically: i == len(...), or some condition satisfied / failed
    if i == END_CONDITION:
        # Handle final state: update answer, return value, etc.
        # e.g., record result, return True/False, or return some number
        ...
        return ...

    # 2) Do work at this step (optional pre-recursion work)
    #    e.g., include nums[i], or skip, or accumulate something
    #    Sometimes you do nothing here and just use i to move
    ...

    # 3) Recursive calls: decide how to move to the next state
    #    Could be:
    #       - recur(i + 1, new_state, other_params)
    #       - multiple branches
    #       - choose + not-choose, etc.

    # Example of single path:
    result1 = recur(i + 1, updated_state_1, other_params)

    # Example of branching paths:
    # path 1: take nums[i]
    # result1 = recur(i + 1, state_if_take, other_params)
    # path 2: skip nums[i]
    # result2 = recur(i + 1, state_if_skip, other_params)

    # 4) Combine results from recursive calls (if needed)
    #    e.g., return result1 or result2 or result1 + result2 etc.
    ...
    return ...

```
