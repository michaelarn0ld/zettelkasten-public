# Technical Interview: Data Structures

## Array
### COMMON OPERATIONS
### WHEN TO USE

## Linked List
### COMMON OPERATIONS
### WHEN TO USE

## Tree
### COMMON OPERATIONS
### WHEN TO USE

## Binary Tree
### COMMON OPERATIONS
* Pre-Order Traversal
```java
void preOrder(Node root) {
    if (root != null) {
        visit(root);
        inOrder(root.left);
        inOrder(root.right);
    }
}
```
* In-Order Traveral [ recursive ]
```java
void inOrder(Node root) {
    if (root != null) {
        inOrder(root.left);
        visit(root);
        inOrder(root.right);
    }
}
```
* In-Order Traveral [ iterative ]
```java
void inOrder(Node root) {
    Stack<Node> stack = new Stack<>();
    Node curr = root;

    while(curr != null || !stack.empty()) {

        while (curr != null) {
            stack.add(curr);
            curr = curr.left;
        }

        curr = stack.pop();
        visit(curr);
        curr = curr.right;
    }
}
```
* Post-Order Traversal
```java
void postOrder(Node root) {
    if (root != null) {
        inOrder(root.left);
        inOrder(root.right);
        visit(root);
    }
}
```
* Level-Order Traversal
```java
void levelOrder(Node root) {
    Queue<Node> q = new LinkedList<>();
    q.add(root);
    while(!q.empty()) {
        Node current = q.pop();
        if (current.left != null) {
            q.add(current.left);
        }
        if (current.right != null) {
            q.add(current.right);
        }
        visit(Node);
    }
}
```
### WHEN TO USE

## Binary Search Tree
### COMMON OPERATIONS
### WHEN TO USE

## Heap
### COMMON OPERATIONS
### WHEN TO USE

## Hash Table
### COMMON OPERATIONS
### WHEN TO USE

## Stack
### COMMON OPERATIONS
### WHEN TO USE

## Queue
### COMMON OPERATIONS
### WHEN TO USE

## Directed Graph
### COMMON OPERATIONS
### WHEN TO USE

## Undirected Graph
### COMMON OPERATIONS
### WHEN TO USE

## Tags
#interview #datastructures
