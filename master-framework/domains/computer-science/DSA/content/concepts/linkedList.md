# LinkedList

## Def

A singly linked list is a fundamental data structure, it consists of nodes where each node contains a data field and a reference to the next node in the linked list. The next of the last node is null, indicating the end of the list. Linked Lists support efficient insertion and deletion operations.

## structure of LinkedList

![linkedlist](https://media.geeksforgeeks.org/wp-content/uploads/20250901170546665785/link1.webp)

```python
# constructor to initialize a new node with data
class Node:
    def __init__(self, new_data):
        self.data = new_data
        self.next = None

# Create the first node (head of the list)
head = Node(10)

# Link the second node
head.next = Node(20)

# Link the third node
head.next.next = Node(30)

# Link the fourth node
head.next.next.next = Node(40)

# printing linked list
temp = head
while temp is not None:
    print(temp.data, end=" ")
    temp = temp.next
```

## LinkedList traversal

```python

# a linked list node
class Node:

    # constructor to initialize a new node with data
    def __init__(self, new_data):
        self.data = new_data
        self.next = None

# function to traverse and print the singly linked list
def traverseList(head):
    while head is not None:
        print(head.data, end="")
        if head.next is not None:
            print(" -> ", end="")
        head = head.next
    print()

if __name__ == "__main__":

    # create a hard-coded linked list:
    # 10 -> 20 -> 30 -> 40
    head = Node(10)
    head.next = Node(20)
    head.next.next = Node(30)
    head.next.next.next = Node(40)

    traverseList(head)
```

### insertion at a specific position

```python
class Node:
    def __init__(self, x):
        self.val = x
        self.next = None

def insertPos(head, pos, val):

    if pos < 1:
        return head

    # head will change if pos = 1
    if pos == 1:
        newNode = Node(val)
        newNode.next = head
        return newNode

    curr = head

    # Traverse to the node just before the new node
    for i in range(1, pos - 1):
        if curr is None:
            return head
        curr = curr.next

    # If position is greater than number of nodes
    if curr is None:
        return head

    newNode = Node(val)

    # update the next pointers
    newNode.next = curr.next
    curr.next = newNode

    return head

def printList(head):
    curr = head
    while curr:
        print(curr.val, end="")
        if curr.next:
            print(" -> ", end="")
        curr = curr.next
    print()

if __name__ == "__main__":
    # Creating the list 1->2->4
    head = Node(1)
    head.next = Node(2)
    head.next.next = Node(4)

    val, pos = 3, 3
    head = insertPos(head, pos, val)
    printList(head)
```

## Deletion at a specific position

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None


def deleteNode(head, position):
    temp = head

    # Head is to be deleted
    if position == 1:
        head = temp.next
        return head

    # Traverse to the node before
    # the one to be deleted
    prev = None
    for i in range(1, position):
        prev = temp
        temp = temp.next

    # Delete the node at the position
    prev.next = temp.next
    return head


def printList(head):
    while head is not None:
        print(f"{head.data} -> ", end="")
        head = head.next
    print("nullptr")


if __name__ == "__main__":
    head = Node(1)
    head.next = Node(2)
    head.next.next = Node(3)
    head.next.next.next = Node(4)

    position = 3
    head = deleteNode(head, position)

    printList(head)
```

## searching

```python

# a Linked List Node
class Node:

  	# constructor to intialize a node with data
    def __init__(self, x):
        self.data = x
        self.next = None

# checks whether key is present in linked list
def search_key(head, key):

    # initialize curr with the head of linked list
    curr = head

    # iterate over all the nodes
    while curr is not None:

        # if the current node's value is equal to key,
        # return true
        if curr.data == key:
            return True

        # move to the next node
        curr = curr.next

    # if there is no node with value as key, return false
    return False

if __name__ == "__main__":

    # create a hard-coded linked list:
    # 1 -> 2 -> 3 -> 4 -> 5
    head = Node(1)
    head.next = Node(2)
    head.next.next = Node(3)
    head.next.next.next = Node(4)
    head.next.next.next.next = Node(5)

    # key to search in the linked list
    key = 5

    if search_key(head, key):
        print("true")
    else:
        print("false")
```

## modifying linkedList

```python
# Python program to modify a singly linked list
# By transferring it to an array
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def countNodes(head):
    count = 0
    curr = head

    while curr is not None:
        count += 1
        curr = curr.next

    return count

def linkedListToArray(head, arr, n):
    curr = head

    for i in range(n):
        arr[i] = curr.data
        curr = curr.next

def arrayToLinkedList(arr, head, n):
    curr = head

    for i in range(n):
        curr.data = arr[i]
        curr = curr.next

def modifyArray(arr, n):

    # Modify the array
    for i in range(n // 2):
        x = arr[i]
        arr[i] = arr[n - i - 1] - x
        arr[n - i - 1] = x

def modifyTheList(head):
    if head.next is None:
        return None

    # Count the number of nodes
    n = countNodes(head)

    # Create an array
    arr = [0] * n

    # Convert linked list to array
    linkedListToArray(head, arr, n)

    # Modify the array
    modifyArray(arr, n)

    # Convert array back to linked list
    arrayToLinkedList(arr, head, n)

    return head

def printList(node):
    curr = node
    while curr is not None:
        print(curr.data, end=" ")
        curr = curr.next
    print()

if __name__ == "__main__":

    # Create a hard-coded linked list
    # 10 -> 4 -> 5 -> 3 -> 6
    head = Node(10)
    head.next = Node(4)
    head.next.next = Node(5)
    head.next.next.next = Node(3)
    head.next.next.next.next = Node(6)

    head = modifyTheList(head)

    printList(head)
```

## reversal of linkedList

```python
class Node:
    def __init__(self, newData):
        self.data = newData
        self.next = None

def reverseList(head):

    curr = head
    prev = None

    # traverse all the nodes of Linked List
    while curr is not None:

        # store next
        nextNode = curr.next

        # reverse current node's next pointer
        curr.next = prev

        # move pointers one position ahead
        prev = curr
        curr = nextNode

    return prev


def printList(node):
    while node is not None:
        print(f"{node.data}", end="")
        if node.next is not None:
            print(" -> ", end="")
        node = node.next
    print()


if __name__ == "__main__":

    head = Node(1)
    head.next = Node(2)
    head.next.next = Node(3)
    head.next.next.next = Node(4)
    head.next.next.next.next = Node(5)
    head = reverseList(head)
    printList(head)
```
