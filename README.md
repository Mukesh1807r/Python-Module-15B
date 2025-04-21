# Binary Search Tree (BST) Construction, Deletion and Display

## 📌 Aim
To write a Python program to build a **Binary Search Tree (BST)** using the `binarytree` module. The program should:
1. Construct a BST from a sorted list.
2. Allow deletion of a node.
3. Rebuild the BST after deletion.
4. Display the tree before and after deletion.

---

## 🛠 Procedure
1. Import the `Node` class from the `binarytree` module.
2. Use a recursive function `_build_bst_from_sorted_values(sorted_values)` to construct a BST from a sorted list.
3. Define the `del_BST(val)` function to delete a node from the BST.
4. Define the `display(T)` function to print the tree values.
5. Take a number from the user to delete from the BST.
6. Show the BST before and after deletion.

---

## 💻 Program

```python
from binarytree import Node

def _build_bst_from_sorted_values(sorted_values):
    if len(sorted_values) == 0:
        return None
    mid_index = len(sorted_values) // 2
    root = Node(sorted_values[mid_index])
    root.left = _build_bst_from_sorted_values(sorted_values[:mid_index])
    root.right = _build_bst_from_sorted_values(sorted_values[mid_index + 1 :])  
    return root

def del_BST(val):
    global x
    if val in x:
        x.remove(val)
        tree = _build_bst_from_sorted_values(sorted(x))
    else:
        return False
    return tree

def display(T):
    for i in T.values:
        print(i, "-->", end="")

x = [5, 3, 6, 2, 4, 1]
print("BST before deletion: ")
t = _build_bst_from_sorted_values(sorted(x))
display(t)

s = int(input())
print("\nBST after deletion: ")
t1 = del_BST(s)
display(t1)
```
---

## Output

![image](https://github.com/user-attachments/assets/56f58d23-73e1-42b6-b95f-4fb8f33c58c7)

---
## Result 

Thus, the program was successfully created and executed to build, delete, and display a Binary Search Tree using a built-in Python module.
