# HashMap

A data structure that stores key–value pairs.

## Core Idea

Uses a hash function to compute an index into an array of buckets, from which the desired value can be found.

## Deep Explanation

- **Hash Function**: Maps keys to indices. Good hash functions minimize collisions.

### Collision Handling

- **Chaining**: Store multiple elements at the same index using linked lists or dynamic arrays.

- **Open Addressing**: Find another empty slot (linear probing, quadratic probing, double hashing).

- **Load Factor**: Ratio of number of elements to number of buckets.

- High load factor → more collisions.

- Resize when load factor exceeds threshold (commonly 0.75).

## Example

Code snippet or diagram.

## Connections

- relates to topic X
- prerequisite for topic Y
