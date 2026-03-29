# Ex. No: 15C - Expression Tree with Inorder and Postorder Traversal

## AIM:
To write a Python program to build the given expression tree and print the inorder and postorder traversals.

---

## ALGORITHM:

1. **Start the program.**
2. Import the required modules (`build` and `Node` from `binarytree`).
3. Define a list `x` representing the expression tree in pre-order fashion (with `None` for missing nodes).
4. Use the `build()` function to generate the binary tree.
5. Print the **inorder** and **postorder** traversal of the tree.
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
