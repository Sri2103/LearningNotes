# Recursion

## Definition and steps

The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called a recursive function.

- **Step1** - Define a base case: Identify the simplest (or base) case for which the solution is known or trivial. This is the stopping condition for the recursion, as it prevents the function from infinitely calling itself.

- **Step2** - Define a recursive case: Define the problem in terms of smaller subproblems. Break the problem down into smaller versions of itself, and call the function recursively to solve each subproblem.

- **Step3** - Ensure the recursion terminates: Make sure that the recursive function eventually reaches the base case, and does not enter an infinite loop.

- **Step4** - Combine the solutions: Combine the solutions of the subproblems to solve the original problem.

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
