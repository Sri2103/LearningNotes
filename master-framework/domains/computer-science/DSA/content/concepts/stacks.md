# Stack

A Stack is a linear data structure that follows a particular order in which the operations are performed. The order may be LIFO(Last In First Out) or FILO(First In Last Out). LIFO implies that the element that is inserted last, comes out first and FILO implies that the element that is inserted first, comes out last.

## Definition

A stack is a linear data structure that follows the Last-In-First-Out (LIFO) principle. It can be implemented using an array by treating the end of the array as the top of the stack.
Short and clear.

## Deep Explanation

In-depth notes

- creating a stack

```python
class myStack:

    def __init__(self, cap):

        # array to store elements
        self.arr = [0] * cap

        # maximum size of stack
        self.capacity = cap

        # index of top element
        self.top = -1
```

## Operations on stack

- **push**
  - Adds an item to the stack. If the stack is full, then it is said to be an Overflow condition.
  - Before pushing the element to the stack, we check if the stack is full.
  - If the stack is full (top == capacity-1) , then Stack Overflows and we cannot insert the element to the stack.
  - Otherwise, we increment the value of top by 1 (top = top + 1) and the new value is inserted at top position .
  - The elements can be pushed into the stack till we reach the capacity of the stack.

```python
def push(self, x):

    if self.top == self.capacity - 1:
        print("Stack Overflow")
        return

    self.top += 1

    self.arr[self.top] = x
```

- **pop**

  - Removes an item from the stack. The items are popped in the reversed order in which they are pushed. If the stack is empty, then it is said to be an Underflow condition. - Before popping the element from the stack, we check if the stack is empty . - If the stack is empty (top == -1), then Stack Underflows and we cannot remove any element from the stack.
  - Otherwise, we store the value at top, decrement the value of top by 1 (top = top – 1) and return the stored top value.

  ```python
  def pop(self):

    if self.top == -1:
        print("Stack Underflow")
        return -1

    value = self.arr[self.top]
    self.top -= 1

    return value
  ```

- **peek**

  - Returns the top element of the stack.
  - Before returning the top element from the stack, we check if the stack is empty.
    If the stack is empty (top == -1), we simply print “Stack is empty”.
    Otherwise, we return the element stored at index = top.

```python

    def peek(self):

        if self.top == -1:
            print("Stack is Empty")
            return -1

        return self.arr[self.top]
```

## Example

Code snippet or diagram.

## Connections

- relates to topic X
- prerequisite for topic Y
