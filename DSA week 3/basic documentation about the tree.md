
**Definition**

- A _tree_ is a hierarchical non-linear data structure made of nodes and edges.
    
- A _binary tree_ is a tree where each node has at most two children (left, right). [baeldung.com+3Wikipedia+3GeeksforGeeks+3](https://en.wikipedia.org/wiki/Binary_tree?utm_source=chatgpt.com)
    
- A binary tree can also be defined recursively: it is either empty or consists of a root node and two binary trees (its left and right sub-trees). [OpenDSA](https://opendsa-server.cs.vt.edu/ODSA/Books/CS3/html/BinaryTree.html?utm_source=chatgpt.com)
    

**Terminology**

- Root: The top node (no parent). [OpenDSA+1](https://opendsa-server.cs.vt.edu/ODSA/Books/CS3/html/BinaryTree.html?utm_source=chatgpt.com)
    
- Parent / Child: If node A points to node B, then A is parent, B is child. [Oxford Robotics](https://www.robots.ox.ac.uk/~vedaldi/assets/teach/2024/b16/notes/4-binary-trees.html?utm_source=chatgpt.com)
    
- Leaf: A node with no children. [baeldung.com+1](https://www.baeldung.com/cs/binary-tree-intro?utm_source=chatgpt.com)
    
- Depth (or level) of a node: Distance from the root. [OpenDSA+1](https://opendsa-server.cs.vt.edu/ODSA/Books/CS3/html/BinaryTree.html?utm_source=chatgpt.com)
    
- Height of a tree: Maximum depth (or max number of edges from root to a leaf) in the tree. [baeldung.com](https://www.baeldung.com/cs/binary-tree-intro?utm_source=chatgpt.com)
    
- Subtree: A node and all its descendants form a subtree. [OpenDSA+1](https://opendsa-server.cs.vt.edu/ODSA/Books/CS3/html/BinaryTree.html?utm_source=chatgpt.com)
    

**Properties & Types**

- Maximum number of nodes in a binary tree of height h is 2h+1−12^{h+1} - 12h+1−1. [Medium+1](https://codingcube.medium.com/a-brief-summary-of-tree-data-structure-1aea26864181?utm_source=chatgpt.com)
    
- Types of binary trees:
    
    - **Full binary tree**: every node has 0 or 2 children. [Medium+1](https://codingcube.medium.com/a-brief-summary-of-tree-data-structure-1aea26864181?utm_source=chatgpt.com)
        
    - **Complete binary tree**: all levels filled except possibly last, and leaf nodes on the last level are as far left as possible. [Medium+1](https://codingcube.medium.com/a-brief-summary-of-tree-data-structure-1aea26864181?utm_source=chatgpt.com)
        
    - **Perfect binary tree**: all internal nodes have two children and all leaves are at the same level. [Medium+1](https://codingcube.medium.com/a-brief-summary-of-tree-data-structure-1aea26864181?utm_source=chatgpt.com)
        
    - **Skewed or degenerate tree**: each internal node has only one child (looks like a linked list). [baeldung.com+1](https://www.baeldung.com/cs/binary-tree-intro?utm_source=chatgpt.com)
        

**Why use Trees / Binary Trees?**

- They model hierarchical data (e.g., folders, categories).
    
- Efficient for search, insertion, deletion when used properly.
    
- Many advanced data structures build on trees: e.g., binary search trees, heaps, tries. [baeldung.com](https://www.baeldung.com/cs/binary-tree-intro?utm_source=chatgpt.com)
    
- Traversals (inorder, preorder, postorder) help visit all nodes in systematic ways. [Interview Cake](https://www.interviewcake.com/concept/java/binary-tree?utm_source=chatgpt.com)
    

**Basic Traversals (Binary Tree)**

- _Inorder_ (Left → Root → Right)
    
- _Preorder_ (Root → Left → Right)
    
- _Postorder_ (Left → Right → Root)  
    These give you different ways to process or “visit” all nodes in a tree. [Wikipedia+1](https://en.wikipedia.org/wiki/Binary_search_tree?utm_source=chatgpt.com)
    

**Implementation Notes**

- Typically each node has value/data + left pointer + right pointer. [baeldung.com](https://www.baeldung.com/cs/binary-tree-intro?utm_source=chatgpt.com)
    
- Binary trees can also be represented using arrays (especially if they are complete) with index relationships: for node at index i: left child = 2i+1, right child = 2i+2 in 0-based index. [Wikipedia+1](https://en.wikipedia.org/wiki/Binary_tree?utm_source=chatgpt.com)