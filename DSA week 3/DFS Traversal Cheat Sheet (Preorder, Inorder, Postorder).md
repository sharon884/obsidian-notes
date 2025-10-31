
## 🔹 Common Concepts

- All are **Depth First Search (DFS)** methods.
    
- All use **recursion** (or can be implemented iteratively using a stack).
    
- Every traversal checks a **base case**:
    
    `if (node === null) return;`
    
- Each recursive call is pushed into the **call stack**.
    
- When a function finishes, it **pops** from the stack and continues from the paused line.
    

---

##  Preorder Traversal

**Order:** `Root → Left → Right`

**Code Example:**

`function preorder(node) {  

if (node === null) return;   

console.log(node.value);  

preorder(node.left); 

preorder(node.right); 

}`

**Example Output:**

`100, 200, 400, 500, 300, 600`

**Why We Use It:**

- Used to **copy or serialize** a tree (root info comes first).
    
- Helps in **creating duplicate trees**.
    
- Useful when you need to **process the root before its children**.
    

---

##  Inorder Traversal

**Order:** `Left → Root → Right`

**Code Example:**

`function inorder(node) {

if (node === null) return;

inorder(node.left);   

console.log(node.value); 

inorder(node.right);

}`

**Example Output:**

`400, 200, 500, 100, 600, 300`

**Why We Use It:**

- In a **Binary Search Tree (BST)**, Inorder traversal gives **nodes in sorted order**.
    
- Used to **check if a tree is a valid BST**.
    
- Ideal when the **left subtree data must be processed before the root**.
    

---

##  Postorder Traversal

**Order:** `Left → Right → Root`

**Code Example:**

`function postorder(node) { 

if (node === null) return;  

postorder(node.left);  

postorder(node.right); 

console.log(node.value); 

}`

**Example Output:**

`400, 500, 200, 600, 300, 100`

**Why We Use It:**

- Used to **delete or free a tree safely** (process children before root).
    
- Useful in **expression trees** for evaluation.
    
- Helpful when you need to **process child nodes first** before the parent.
    

---

## Quick Comparison

|Traversal|Order|Root Position|Common Use|
|---|---|---|---|
|Preorder|Root → Left → Right|**First**|Copy or serialize a tree|
|Inorder|Left → Root → Right|**Middle**|Sorted order in BST|
|Postorder|Left → Right → Root|**Last**|Delete tree / Expression evaluation|

---

##  Memory Trick

|Step|Preorder|Inorder|Postorder|
|---|---|---|---|
|1️⃣|Root first|Left first|Left first|
|2️⃣|Then Left|Then Root|Then Right|
|3️⃣|Then Right|Then Right|Root last ✅|
