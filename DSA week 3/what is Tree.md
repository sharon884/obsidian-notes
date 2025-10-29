
### 🌲 What Is a Tree in DSA?

---

1. **Definition**

A **Tree** is a **non-linear**, **hierarchical data structure** that connects elements called **nodes** using **edges** (links).

It’s called “hierarchical” because it looks like a family tree — one node at the top (root) and branches going down.

---

### 🌳 2. **Structure of a Tree**

Each element in a tree is called a **node**, and the topmost node is the **root**.

Each node may connect to **child nodes**, and those child nodes can also have their own children — forming a hierarchy.

Example:

        `A  
		
         / \    
           
	     B   C  
	      
	    / \   \   
	  
		D   E   F`

In this tree:

- **A** → root node
    
- **B, C** → children of A
    
- **D, E, F** → leaf nodes (no children)
    
- **Edges** → the lines connecting nodes (A→B, A→C, etc.)
    

---

### ⚙️ 3. **Tree Terminology**

Here’s a mini dictionary you’ll use all the time:

|Term|Meaning|
|---|---|
|**Root**|The topmost node (no parent)|
|**Parent**|Node with one or more children|
|**Child**|Node that descends from a parent|
|**Leaf**|Node with no children|
|**Edge**|Connection between two nodes|
|**Path**|Sequence of connected nodes|
|**Height**|Longest path from root to a leaf|
|**Depth**|Distance from root to a specific node|
|**Subtree**|A smaller tree formed from any node and its descendants|

---

### 🧠 4. **Why Trees Are Important**

Trees are _everywhere_ in computer science.  
They help organize data efficiently and make searching, sorting, and storing fast.

|Type|Real Use Case|
|---|---|
|**Binary Search Tree (BST)**|Searching numbers/words efficiently|
|**Heap**|Priority queues, scheduling|
|**Trie**|Autocomplete, spell check|
|**Syntax Tree**|Used in compilers/interpreters|
|**DOM Tree**|In browsers to render web pages|
|**File System Tree**|Directories/folders on your computer|

---

### 🌿 5. **Tree vs Other Data Structures**

|Type|Structure|Example|
|---|---|---|
|**Array / Linked List**|Linear (one after another)|[1,2,3,4]|
|**Tree**|Non-linear (hierarchical)|Root → branches|
|**Graph**|Non-linear (but can have cycles)|Social networks|

Tree = _special type of graph_ (no cycles).

---

### 🧩 6. **Properties of a Tree**

If a tree has **N nodes**, it always has **N – 1 edges**  
(Each connection joins two nodes except the root).

---

### ⚡ 7. **Basic Types of Trees**

|Type|Description|
|---|---|
|**General Tree**|Any number of children|
|**Binary Tree**|At most 2 children (left, right)|
|**Binary Search Tree (BST)**|Left < Root < Right|
|**Balanced Tree (AVL, Red-Black)**|Keeps height small|
|**Complete Tree**|All levels filled except last|
|**Full Tree**|Every node has 0 or 2 children|
|**Perfect Tree**|All leaves at same level|
|**Trie (Prefix Tree)**|Stores strings character by character|
|**Heap (Min/Max)**|Used in priority queues|

---

### 🎯 In Simple Words

> A **Tree** is like a family hierarchy or folder system.  
> The **root** is the top, each **child** is a subfolder, and **leaves** are items at the end.