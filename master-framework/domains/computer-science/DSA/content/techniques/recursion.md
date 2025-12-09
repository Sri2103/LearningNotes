# Recursion

A programming technique where a function calls itself to solve smaller versions of the same problem.

Breaks a big problem into smaller subproblems until reaching a base case.

Often used in problems with repetitive or nested structures (trees, graphs, sequences).

## key Concepts

- **Recursive Function** → A function that calls itself.

- **Base Case** → The condition that stops recursion (smallest problem solved directly).

- **Recursive Case** → The part where the function calls itself with smaller input.

- **Stack** → Recursion uses the call stack to keep track of function calls.

- **Termination** → Ensuring recursion eventually stops at the base case.

- **Infinite Recursion** → Happens if no proper base case is defined.

## Definition and steps

The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called a recursive function.

- **Step1** - Define a base case: Identify the simplest (or base) case for which the solution is known or trivial. This is the stopping condition for the recursion, as it prevents the function from infinitely calling itself.

- **Step2** - Define a recursive case: Define the problem in terms of smaller subproblems. Break the problem down into smaller versions of itself, and call the function recursively to solve each subproblem.

- **Step3** - Ensure the recursion terminates: Make sure that the recursive function eventually reaches the base case, and does not enter an infinite loop.

- **Step4** - Combine the solutions: Combine the solutions of the subproblems to solve the original problem.

## 🔄 Process Flow

- Define the base case (when to stop).

- Define the recursive case (how to reduce the problem).

- Each recursive call reduces the problem size.

- Eventually, recursion reaches the base case and unwinds back.

## Example

```python
def sum(n):

    # base condition
    if n == 1:
        return 1

    return n + sum(n - 1)

if __name__ == "__main__":
    n = 5
    print(sum(n))
```

```python
def factorial(n):
    if n == 0:          # 🏁 Base Case
        return 1
    return n * factorial(n - 1)  # 🔄 Recursive Case

def array_sum(arr):
    if not arr:         # 🏁 Base Case
        return 0
    return arr[0] + array_sum(arr[1:])  # 🔄 Recursive Case

```

## Need of Recursion?

- Recursion helps in logic building. Recursive thinking helps in solving complex problems by breaking them into smaller subproblems.
- Recursive solutions work as a a basis for Dynamic Programming and Divide and Conquer algorithms.

## Applications of Recursions

1. **Tree and Graph Traversal**: Used for systematically exploring nodes/vertices in data structures like trees and graphs.
2. **Sorting Algorithms**: Algorithms like quicksort and merge sort divide data into subarrays, sort them recursively, and merge them.
3. **Divide-and-Conquer Algorithms**: Algorithms like binary search break problems into smaller subproblems using recursion.
4. **Fractal Generation**: Recursion helps generate fractal patterns, such as the Mandelbrot set, by repeatedly applying a recursive formula.
5. **Backtracking Algorithms**: Used for problems requiring a sequence of decisions, where recursion explores all possible paths and backtracks when needed.
6. **Memoization**: Involves caching results of recursive function calls to avoid recomputing expensive subproblems. These are just a few examples of the many applications of recursion in computer science and programming. Recursion is a versatile and powerful tool that can be used to solve many different types of problems.

## Where Recursion is Used

- **Mathematical problems** → Factorial, Fibonacci.

- **Tree traversal** → Preorder, Inorder, Postorder.

- **Graph traversal** → DFS.

- **Divide and Conquer algorithms** → Merge Sort, Quick Sort.

- **Backtracking problems** → Sudoku, N-Queens, Maze solving.

## Patterns

- You solve ONE piece and trust recursion to solve the rest.

You should think Recursion when you see:

- ✅ Trees

- ✅ Graph DFS

- ✅ Backtracking

- ✅ Divide & Conquer

- ✅ Nested structures

- ✅ “Do same thing on smaller input”

- ✅ “All possibilities”

**big recursion pattern**:

| Order            | Used When                              |
| ---------------- | -------------------------------------- |
| Decide → Recurse | Build forward (merge, construct)       |
| Recurse → Decide | Fix after future (delete, reverse, DP) |

**Generic structure**:

```python
PRE-ORDER:
[ DO WORK ] → recurse → recurse → recurse

POST-ORDER:
recurse → recurse → recurse → [ DO WORK ]
```

- Pre-order → Do your work BEFORE going down

| Problem Type          | Why                                 |
| --------------------- | ----------------------------------- |
| Building structures   | You must create before going deeper |
| Merging lists (LC 21) | You pick the head first             |
| Tree creation         | You build parent before children    |
| DFS printing          | Visit node before children          |

```python
# Decide → Recurse (Preorder)
def solve(x):
    if base_case(x):
        return base_value

    decision = make_decision(x)
    return solve(reduced_x)

```

```python
# Recurse → Decide (Postorder)
def solve(x):
    if base_case(x):
        return base_value

    result = solve(reduced_x)
    return decide_using(result)

```

| Problem Type            | Why                               |
| ----------------------- | --------------------------------- |
| Deleting nodes          | You must know final `next`        |
| Reversing list (LC 206) | You must flip after tail is ready |
| Tree DP                 | Parent depends on children        |
| Evaluating expressions  | Operands before operator          |

## Summary

- Recursion = Function calling itself to solve smaller problems.

- Needs a base case to stop.

- Powerful for problems with repetitive or nested structures.

- Must be used carefully to avoid infinite loops or stack overflow.
