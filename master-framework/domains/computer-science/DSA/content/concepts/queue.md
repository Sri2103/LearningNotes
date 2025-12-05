# Queue

A Queue Data Structure is a fundamental concept in computer science used for storing and managing data in a specific order.

## usecases

- It follows the principle of "First in, First out" (FIFO), where the first element added to the queue is the first one to be removed.
- It is used as a buffer in computer systems where we have speed mismatch between two devices that communicate with each other. For example, CPU and keyboard and two devices in a network
- Queue is also used in Operating System algorithms like CPU Scheduling and Memory Management, and many standard algorithms like Breadth First Search of Graph, Level Order Traversal of a Tree.

## Definition

Short and clear.
![def](https://media.geeksforgeeks.org/wp-content/uploads/20250827110558739481/Dequeue-Operation-in-Queue-1.webp)

## Deep Explanation

In-depth notes.
![queue](https://media.geeksforgeeks.org/wp-content/uploads/20250917154046246598/Types-of-Queue.webp)

- **Basic Terminologies of Queue**

- **Front** : Position of the entry in a queue ready to be served, that is, the first entry that will be removed from the queue, is called the front of the queue. It is also referred as the head of the queue.
- **Rear** : Position of the last entry in the queue, that is, the one most recently added, is called the rear of the queue. It is also referred as the tail of the queue.
- **Size**: Size refers to the current number of elements in the queue.
  Capacity: Capacity refers to the maximum number of elements the queue can hold.

- **operations**
  Queue is a linear data structure that follows the FIFO (First In First Out) principle, where insertion is done at the rear end and deletion is done from the front end.

The following are some fundamental operations that allow us to add, remove, and access elements efficiently.

- **enqueue()** - Insertion of elements to the queue.

```python
from collections import deque

if __name__ == "__main__":
    q = deque()

    # inserting elements at rear
    q.append(10)
    q.append(20)
    q.append(30)
```

- **dequeue()** - Removal of elements from the queue.

```python
from collections import deque

if __name__ == "__main__":
    q = deque()

    # inserting elements at rear
    q.append(1)
    q.append(8)
    q.append(3)

    # deleting element from front
    q.popleft()
```

- **getFront()** - Acquires the data element available at the front node of the queue without deleting it.

```python
from collections import deque

if __name__ == "__main__":

    q = deque()

    # inserting elements at rear
    q.append(1)
    q.append(8)
    q.append(3)

    # getting the front element
    print(q[0])
```

- **getRear()** - This operation returns the element at the rear end without removing it.

```python
from collections import deque

if __name__ == "__main__":
    q = deque()

    q.append(1)
    q.append(8)
    q.append(3)

    # get rear element
    print(q[-1])
```

- **isEmpty()** - Checks if the queue is empty.

```python
from collections import deque

if __name__ == "__main__":
    q = deque()

    q.append(5)
    q.append(9)

    # check if queue is empty
    if not q:
        print("Queue is empty")
    else:
        print("Queue is not empty")
```

- **size()** - This operation returns the size of the queue i.e. the total number of elements it contains.

```python
from collections import deque

if __name__ == "__main__":
    q = deque()

    q.append(2)
    q.append(7)
    q.append(4)

    # get size of queue
    print(len(q))
```

## Example

Code snippet or diagram.

[book](https://www.geeksforgeeks.org/dsa/applications-advantages-and-disadvantages-of-queue/)

## Connections

- relates to topic X
- prerequisite for topic Y
