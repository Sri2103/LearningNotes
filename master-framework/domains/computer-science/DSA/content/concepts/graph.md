# Graph

A graph is a non-linear data structure made up of vertices (nodes) and edges (connections) that represent relationships between objects. Unlike arrays or linked lists, graphs do not follow a sequential order.

![graph](https://media.geeksforgeeks.org/wp-content/uploads/20251024112600799492/introduction_to_graphs.webp)

## components of graph

- **Vertices**: Vertices are the fundamental units of the graph. Sometimes, vertices are also known as vertex or nodes. Every node/vertex can be labeled or unlabelled.
- **Edges** : Edges are drawn or used to connect two nodes of the graph. It can be ordered pair of nodes in a directed graph. Edges can connect any two nodes in any possible way. There are no rules. Sometimes, edges are also known as arcs. Every edge can be labelled/unlabelled.

## Type of graphs

A graph can be divided into multiple categories based on different properties such as edges, direction, connectivity and many others.

### Based on weight

- **Weighted Graphs**
  A weighted graph is a graph where each edge has a number (weight) that represents distance, cost, or time.

  ![alt text](https://media.geeksforgeeks.org/wp-content/uploads/20250220130152745825/w-660.webp)

- **Unweighted Graphs**
  An unweighted graph is a graph where all edges are treated equally, with no extra values like distance or cost.

  ![alt text](https://media.geeksforgeeks.org/wp-content/uploads/20250220130157480056/dense.webp)

### Based on direction

- undirected graph
  A graph in which edges do not have any direction. That is the nodes are unordered pairs in the definition of every edge.

- directed graph
  A graph in which edge has direction. That is the nodes are ordered pairs in the definition of every edge.
  ![alt text](https://media.geeksforgeeks.org/wp-content/uploads/20200630114438/directed.jpg)

- More graphs: [see more](https://www.geeksforgeeks.org/dsa/graph-types-and-applications/)

## Traversal of graphs

Traversal techniques are used to visit all the vertices of a graph systematically. These methods help to explore the graph completely and are useful for solving many graph-related problems.

### DFS

- Explores as far as possible along each branch before backtracking.
- Uses a stack (or recursion).
- detail info: [dfs-graph](https://www.geeksforgeeks.org/dsa/depth-first-search-or-dfs-for-a-graph/)

### BFS

- Explores all neighbors of a vertex before moving to the next level.
- Uses a queue.
- detail info: [bfs-graph](https://www.geeksforgeeks.org/dsa/breadth-first-search-or-bfs-for-a-graph/)
