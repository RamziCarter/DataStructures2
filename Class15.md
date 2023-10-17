#### Trees

A tree is a collection of nofes connected by edges. 
As with a linked list each node can have a piece of data

A tree cannot contain any "cycles"

> Tree Vocabulary
- root
  - top of the tree
- The node that its connected to are called child nodes
- if a nod has no children it is called a leaf
- The height of the tree is the number of edges from root to leaf
- The depth of a node, is how many edges it is away from the root

---
Binary Tree

- a binary tree is where each node has at most two childress
- a subtree is a section of a larger tree

  Node has a left.right childe

  Traversing a tree
  - pre order traversal
    - process root, recurse left, recurse right 
  - post order traversal
    - recurse left, recurse right, process root
  - in order traversal
    - process left, process root, process right
   
  Searching a binary search tree is very similar to running the binary search algorithm on a sorted list
  Instead of recursing on different indextes we recurse on the left or right childer
---
Runtime O(H), where H is the height of the tree
- best case scenario is O(Log(n))

To guarentee O(log(n)) run time, we need to add some rules about the tree structure
- the height of the subtrees need to be balanced
- in a balanced tree the hight of the laft and right subtrees can differ by no more than 1

Balance Factor = height(left subtree) - height(right subtree)


---
> Rotations
- If a tree becomes unbalanced, you need to "rotate" the tree
- A height-balanced Binary Search Tree is called an AVL tree
