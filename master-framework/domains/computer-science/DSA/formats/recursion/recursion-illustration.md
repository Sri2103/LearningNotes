# 🧠 Framework for Creating Recursion Trees (Universal Template)

## 📌 Step 0 — Identify the Recursive Function Signature

- Write down the function in terms of parameters.

```code
add(l1, l2, carry)
swapPairs(head)
mergeSort(arr)
dfs(node, path)

```

- represents the what state each recursion node represents

## Step 1 — Identify Branching Type (Structure of Tree)

Recursion trees have three basic shapes:

### 1️⃣ Linear (1 recursive call)

Examples:
Reverse linked list (LC 206)

Swap pairs (LC 24)

Add two numbers (LC 2)

```code
call → call → call → base

```

### 2️⃣ Binary (2 recursive calls)

Examples:

Merge sort

Max subarray

LC 395

Shape:

```code
        call
       /    \
   call    call

```

### 3️⃣ Multi-branch (K recursive calls)

Examples:

Subsets

Permutations

N-Queens

Backtracking

```code

      call
   /  |   \
  c   c    c

```

- Identifying the shape determines how your recursion tree expands

## Step 2 — Label the Current Node With

Each node in the recursion tree should show:

The function call (its parameters)

The decision made at this level

The local result (partial computation)

The recursive calls triggered

```code
function(params)
│
├── local action / decision
└── recursive calls

```

Example

```code
add(2,5,0)
│
├── sum=7 carry=0
└── next = add(4,6,0)
```

## Step 3 — Draw Child Nodes for Each Recursive Call

This is where branching happens

If a function calls

```code
return f(a) + f(b)

```

Tree

```code
          f(x)
         /    \
     f(a)     f(b)

```

if liner recursion

```code
f(x)
 │
 ↓
f(next)

```

## Step 4 — Show the Base Case Clearly

Every recursion tree ends at a leaf

Draw leaf node for

```code
if base condition:
    return something

```

Example:

```code
add(None, None, 0)
└── return None
```

Example:

```code
if n == 1:
  return arr

```

## Step 5 — Show the Return Flow (Bottom-Up Reconstruction)

This is the most important part most people forget.

Once leaves return, the parent node:

receives child results

combines them

returns upward

diagram style:

```code
child1 returns A
child2 returns B
parent returns combine(A, B)

```

Example (LC 24):

```code
swap(5) returns 5
↑
swap(3,4) returns 4→3→5
↑
swap(1,2) returns 2→1→4→3→5
```

## Step 6 — Add Annotations for Explanation

Add small comments:

“This is where we split the array”

“This is where we swap pair”

“This is where carry is added”

“This is where recursion stops”

“This is the return path”

These annotations make recursive behavior transparent to the reader.

## Step 7 — Summarize Final Structure

```code
function(params)
│
├── Local action / decision at this level
├── Info (value, carry, swap, operator, etc.)
└── Recursive calls:
       ├── function(child_params_1)
       ├── function(child_params_2)
       └── ...

# Base Case:
function(base_params)
└── return base_value

# Return Flow:
child_1_result
child_2_result
...
combined_result = combine(child_results)
return combined_result
```

🧠 Essence of a Recursion Tree (final one-liner)

> A recursion tree shows how a problem is broken down (top-down)
> and how the solution is rebuilt (bottom-up).
