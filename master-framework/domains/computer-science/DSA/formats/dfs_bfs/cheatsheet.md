# 🧠 DFS & BFS — One-Page CHEATSHEET (Framework-Aligned)

## 1️⃣ CORE IDEA (Anchor this first)

| Concept         | DFS                            | BFS                   |
| --------------- | ------------------------------ | --------------------- |
| Traversal style | Go deep first                  | Go wide first         |
| Control         | Recursion (stack)              | Queue                 |
| State storage   | Call stack                     | Explicit queue        |
| Best for        | Paths, backtracking, structure | Shortest path, levels |
| Natural form    | Recursive                      | Iterative             |

## 2️⃣ UNIVERSAL FRAMEWORK MAPPING

```code
(index i) + (state) + (move to next)

```

| Framework Term | DFS              | BFS                    |
| -------------- | ---------------- | ---------------------- |
| `i` (index)    | current node     | node popped from queue |
| `state`        | visited / path   | visited / level        |
| recursion      | explore neighbor | push to queue          |
| base case      | visited / stop   | queue empty            |

## 3️⃣ DFS — CHEATSHEET

### pseudo code

```python
def dfs(node, state, graph):

    # 1) Base case (STOP)
    if node in state.visited:
        return

    # 2) Do work (PRE-ORDER)
    state.visited.add(node)
    process(node)

    # 3) Recursive calls (MOVE)
    for neighbor in graph[node]:
        dfs(neighbor, state, graph)

    # 4) Cleanup (POST-ORDER, optional)
    # state.visited.remove(node)  # for backtracking problems
```

### when to use

✅ Path existence
✅ All possible paths
✅ Tree / graph structure
✅ Backtracking problems

### DFS — Mental Sentence

```code
“From this node, go as deep as possible, then come back.”
```

## 4️⃣ BFS — CHEATSHEET

### pseudo code- bfs

```python
def bfs(start, graph):

    queue = Queue()
    visited = set()

    # Initialization
    queue.push(start)
    visited.add(start)

    # Loop = recursion replacement
    while not queue.empty():

        # 1) Current index
        node = queue.pop()

        # 2) Do work
        process(node)

        # 3) Move to next states
        for neighbor in graph[node]:
            if neighbor not in visited:
                visited.add(neighbor)
                queue.push(neighbor)

```

### 🔹 BFS — When to Use

✅ Shortest path (unweighted)
✅ Minimum steps
✅ Level-wise processing
✅ Distance problems

### 🔹 BFS — Mental Sentence

> “Process everything at this depth, then move one level deeper.”

## 5️⃣ VISUAL ILLUSTRATION (KEY DIFFERENCE)

```code
        A
      /   \
     B     C
    / \     \
   D   E     F

```

### 🔁 DFS Traversal Order

> A → B → D → (back) → E → (back) → C → F

### DFS recursion stack

```code
dfs(A)
 └── dfs(B)
     └── dfs(D)
     └── dfs(E)
 └── dfs(C)
     └── dfs(F)
```

![DFS](https://he-s3.s3.amazonaws.com/media/uploads/9fa1119.jpg?utm_source=chatgpt.com)

### 🔁 BFS Traversal Order

> A → B → C → D → E → F

### BFS Queue State

```css
[A]
[B, C]
[D, E, F]
```

## 6️⃣ DFS vs BFS — SIDE-BY-SIDE MEMORY TABLE

| Question              | DFS        | BFS            |
| --------------------- | ---------- | -------------- |
| Uses recursion?       | ✅ Yes     | ❌ No          |
| Uses queue?           | ❌ No      | ✅ Yes         |
| Finds shortest path?  | ❌ No      | ✅ Yes         |
| Memory usage          | Path depth | Width of level |
| Backtracking friendly | ✅ Yes     | ❌ No          |

## 7️⃣ PROBLEM RECOGNITION TRIGGERS 🚨

**Choose DFS if you see:**

- “All possible…”

- “Does a path exist”

- “Backtracking”

- Tree structure

**Choose BFS if you see:**

- “Minimum steps”

- “Shortest path”

- “Levels”

- “Nearest / closest”

## ONE-LINE FINAL INTUITION (VERY IMPORTANT)

> DFS = recursion chooses depth immediately
> BFS = queue delays depth until siblings are done
