# BFS / DFS

## DFS

- A graph/tree traversal technique that explores nodes deeply first.

- Starts from a source node and goes as far as possible along one path before backtracking.

- Uses recursion or a stack.

## Key Concepts

- **Node** → A point in the graph/tree.

- **Edge** → A connection between two nodes.

- **Stack / Recursion** → Used to keep track of nodes during exploration.

- **Visited Set** → Keeps track of nodes already explored.

- **Backtracking** → Returning to previous nodes when stuck.

## process flow

- Start at the source node.

- Visit it and mark as visited.

- Recursively (or via stack) visit each unvisited neighbor.

- If no neighbors left, backtrack.

- Continue until all nodes are visited.

```python

def dfs(graph, start, visited=None):
    if visited is None:
        visited = set()

    print(start)          # Visit node
    visited.add(start)

    for neighbor in graph[start]:
        if neighbor not in visited:
            dfs(graph, neighbor, visited)

```

---

## BFS

A graph/tree traversal technique that explores nodes level by level.

Starts from a source node and visits all neighbors before moving deeper.

Uses a queue to keep track of nodes to visit next.

## 🔄 Process Flow

Put the starting node in the queue.

While the queue is not empty:

Remove the front node.

Visit it.

Add all its unvisited neighbors to the queue.

Repeat until all reachable nodes are visited.

```python
from collections import deque

def bfs(graph, start):
    visited = set()
    queue = deque([start])

    while queue:
        node = queue.popleft()  # FIFO
        if node not in visited:
            print(node)          # Visit node
            visited.add(node)
            for neighbor in graph[node]:
                if neighbor not in visited:
                    queue.append(neighbor)


```
