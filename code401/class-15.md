# Class 15 - Trees

[<== Main Page](../README.md)
[<== Code 401](../code401/code401.md)

## Readings

- [Trees](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/Trees.html)

  - Three types of trees, binary, binary search and k-ary trees.
    - Binary trees can only have 2 child nodes, left and right.
    - K-ary trees can have K number of child nodes.
    - Binary search trees have nodes organized in a manner where all values that are smaller than the root are placed to the left, and all values that are larger than the root are placed to the right.

  - Two types of traversing trees, depth first and breadth first.
    - Depth first prioritizes going through the depth (height) of the tree first
      - Pre-order: root >> left >> right
      - In-order: left >> root >> right
      - Post-order: left >> right >> root

    - Breadth first prioritizes going through the depth (height) of the tree first
      - It will go through any child nodes from the queue before moving onto the next child node and its children.
      - K-ary trees go through the same level of children nodes before moving on to the next levell of children, where Binary will go the entire 'breadth' of the tree from parent through last child of left child node first, then move on to the the right child node and go down through last child.
  
  - Searching a Binary Search Tree compares the node you are searching for against the root of the tree or sub-tree. If the value is smaller, you only traverse the left side. If the value is larger, you only traverse the right side.
    - Best searched with a while loop.

## Vocab

- Node - A Tree node is a component which may contain it’s own values, and references to other nodes
- Root - The root is the node at the beginning of the tree
- K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
- Left - A reference to one child node, in a binary tree
- Right - A reference to the other child node, in a binary tree
- Edge - The edge in a tree is the link between a parent and child node
- Leaf - A leaf is a node that does not have any children
- Height - The height of a tree is the number of edges from the root to the furthest leaf

## Things I Want To Know More About

- Class notes

- Career Coaching
