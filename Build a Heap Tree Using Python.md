# Ex. No: 15D - Build a Heap Tree Using Python

## AIM:
To write a Python program to build a heap tree using appropriate Python package and function.

---

## ALGORITHM:

1. **Start the program.**
2. Import the `heapq` module.
3. Define a function `heaptree(H)` that takes a list `H` as input.
4. Use `heapq.heapify(H)` to convert the list into a min-heap.
5. Print the created heap.
6. **End the program.**

---
## Program

```
class Node:
    def __init__(self, val, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right
 

def isLeaf(node):
    return node.left is None and node.right is None
 
def process(op, x, y):
    if op == '+':
        return x + y
    if op == '-':
        return x - y
    if op == '*':
        return x * y
    if op == '/':
        return x / y
 
def evaluate(root):

    if root is None:
        return 0
  
    if isLeaf(root):
        return float(root.val)
    
    x = evaluate(root.left)
    y = evaluate(root.right)
    return (process(root.val, x, y))
    


root = Node('/')
root.left = Node('*')
root.right = Node('+')
root.left.left = Node('+')
root.left.right = Node(4)
root.right.left = Node('-')
root.right.right = Node(2)
root.left.left.left = Node(3)
root.left.left.right = Node(1)
root.right.left.left = Node(9)
root.right.left.right = Node(5)
print('The value of the expression tree is',evaluate(root))

```

## OUTPUT
![Screenshot 2025-05-05 005758](https://github.com/user-attachments/assets/797eb3fa-b809-4c88-abe3-9f7bcf3c2faf)


## RESULT
Thus The result of the expression tree evaluation is the computed value derived from traversing the tree and applying the operations based on the operator nodes and operand values at the leaf nodes.
