
A ****Binary Search Tree (BST)**** is a type of binary tree data structure in which each node contains a unique key and satisfies a specific ordering property:

- All nodes in the left subtree of a node contain values ****strictly less**** than the node’s value.
- All nodes in the right subtree of a node contain values ****strictly greater**** than the node’s value.

This structure enables efficient operations for searching, insertion, and deletion of elements, especially when the tree remains balanced.

![bst1.webp](https://media.geeksforgeeks.org/wp-content/uploads/20250904151404492797/bst1.webp)![bst1.webp](https://media.geeksforgeeks.org/wp-content/uploads/20250904151404492797/bst1.webp)

### Key Characteristics of a BST:

- ****Hierarchical Structure****: A BST is composed of nodes, each having up to two children, forming a tree-like hierarchy with a single root node at the top.
- ****Ordering Property****: For every node in the BST, all values in the left subtree are smaller, and all values in the right subtree are larger than the node’s value. This rule holds recursively for all subtrees.
- ****Efficient Operations****: In a balanced BST, operations like search, insertion, and deletion can be performed in ****O(log n)**** time. In the worst-case (unbalanced), these degrade to ****O(n)****. With self-balancing BSTs like AVL and Red Black Trees, we can ensure the worst case as O(Log n).
- ****Recursive Nature****: Each left or right subtree of a node in a BST is itself a BST, allowing recursive algorithms to naturally process the tree.
- ****Practical Applications****: BSTs are widely used in database indexing, symbol tables, range queries, and are foundational for advanced structures like AVL trees, Red-Black trees. In problem solving, BSTs are used in problems where we need to maintain sorted stream of data.