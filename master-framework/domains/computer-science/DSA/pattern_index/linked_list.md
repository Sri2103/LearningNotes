# ✅ Linked List Problem-Solving Patterns — Master Notes

Key patterns for solving Linked List problems efficiently (LeetCode-style).

---

## 1️⃣ Dummy Node Technique

**What:** Add a fake node before head to handle edge cases.  
**Why:** Simplifies head manipulation and deletion logic.  
**Use When:** Head may change → use a dummy node.  
**Common Uses:** Remove nodes, deduplicate, merge, partition, reverse sublists.

---

## 2️⃣ Two Pointer Technique

**What:** Two pointers with different speeds or roles.  
**Variants:**

- Fast & Slow → find middle, detect cycle
- Read & Write → overwrite-based problems
- Prev & Curr → deletion/reversal  
  **Use Cases:** Find middle, remove nth node, detect cycle, deduplication, in-place update.

---

## 3️⃣ Stable Partition

**What:** Split list while preserving order.  
**Example:**  
`< x → group A`, `≥ x → group B`  
**Use Cases:** Partition by value, even–odd split, condition grouping.  
**Property:** Maintain order within groups.

---

## 4️⃣ Two List Construction & Merge

**Idea:** Build two lists and then merge for cleaner logic.  
**Template:**

```

small = dummy1
large = dummy2
for node in lst:
if condition:
small.next, small = node, node
else:
large.next, large = node, node
large.next = None
small.next = dummy2.next

```

**Benefits:** Stable, O(n), O(1) space, simple.

---

## 5️⃣ Duplicate Block Skipping

**Goal:** Remove duplicate _blocks_ entirely (not just reduce).
**Logic:** Detect → skip → reconnect.
**Used In:** Remove all duplicates from sorted list.

---

## 6️⃣ In-Place Reversal

**Core Pointers:** `prev ← curr → next`
**Use Cases:** Reverse list, reverse subrange, reverse k-group.

---

## 7️⃣ Cycle Detection

**Rule:** If fast meets slow → cycle exists.
**Extensions:** Find cycle entry, detect happy numbers.

---

## 8️⃣ Circular Linking Trick

**What:** Temporarily connect tail → head (`tail.next = head`).
**Used For:** Rotate, shift, rewire portions.

---

## 🔍 Quick Pattern Guide

| Problem Type            | Best Pattern                 |
| ----------------------- | ---------------------------- |
| Head may change         | Dummy Node                   |
| Grouping by condition   | Two Lists / Stable Partition |
| Remove duplicates fully | Duplicate Block Skipping     |
| Reverse operations      | In-place Reversal            |
| Detect cycles           | Fast–Slow Pointer            |
| Rotate / Shift          | Circular Linking             |

---

```python
# linkedlist operation on using linkedlist
def solve(head):
    if not head:
        return None

    head.next = solve(head.next)

    if should_delete(head):
        return head.next
    else:
        return head

```
