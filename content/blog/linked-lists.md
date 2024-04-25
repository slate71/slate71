+++
title = "Notes on Linked Lists"
date = "2024-04-11T11:24:40-07:00"
description = "Notes on working with Linked Lists."
tags = ["data-structures"]
draft = true
+++

## Some notes about working with Linked Lists

### Types of Linked Lists

There are 3 types of linked lists:

1. **Singly**
2. **Doubly**
3. **Circular**

Linked lists are a graph in which each node has at most one child and no siblings. **Singly** linked lists have a reference to the child node, often refered to as the `next` node to denote a sequence, but not the parent or `prev` (previous) node. **Doubly** linked lists are bi-directional and reference the child or `next` node as well as the parent or `prev` node. **Circular** linked lists contain a tail node that points back to the head node creating a circular chain.

### Common Operations

- **Traversal** Iteration or recursion
- **Insertion**
- **Deletion**
- **Search**

### Advantages

- **Dynamic Sizing**
- **Efficient Insertion/Deletion**

### Disadvantages

- **Direct Access**
- **Memory Overhead**

### Creating a Linked List

TypeScript

```ts
interface LinkedList {
  val: number;
  next: LinkedList;
}
```

Python

```py
class Node {
  def __init__(self, data: int):
    self.data: int = data
    self.next: Node = None
}
```

Go

```go
type struct Node {
  Data int
  Next *Node
}
```
C

```c
typedef struct Node {
  int data;
  struct Node* next;
} Node;
```

### The "Runner" Technique

### Recursive Problems

### Dummy Head Nodes

Often times, it is handy to create a dummy head node when working with singly linked lists.

```typescript
const dummyNode = new LinkedListNode(null, head);
```

This makes it easier to operate on the `head` node. If it needs to be removed, for example:

```ts
// Remove the current head node
dummyNode.next = dummyNode.next.next;
```
