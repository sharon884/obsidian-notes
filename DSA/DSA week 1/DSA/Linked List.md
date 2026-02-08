
## 🧠 **Linked List — Complete Notes**

### 📘 **Definition**

A **Linked List** is a **linear data structure** where elements (called **nodes**) are stored **non-contiguously** in memory and linked using **pointers**.

Each node typically has **two parts**:

1. **Data** → stores the actual value.
    
2. **Pointer (next)** → stores the memory address of the next node



### ⚙️ **Internal Workflow**

- When a new node is created, it is stored in the **heap memory** (because it’s dynamically allocated).
    
- The **“next” pointer** of one node holds the **address/reference** of the next node in the sequence.
    
- The **head** pointer holds the address of the first node in the list.
    
- The **last node** has its next pointer set to **NULL**, indicating the end of the list.
    

`HEAD → [Data | Next] → [Data | Next] → [Data | NULL]`

🧩 **Memory Representation (Example)**

|Node|Data|Next (address)|
|---|---|---|
|n1|10|204|
|n2|20|356|
|n3|30|NULL|

So in memory, data isn’t continuous like an array — it’s scattered, but linked by the pointers.



### 🧱 **Why Heap Memory?**

- Arrays are allocated in the **stack** or **static memory**, meaning their size is fixed.
    
- Linked Lists need to **grow/shrink dynamically**, so they are allocated in the **heap memory** using dynamic allocation (`new` in JS/Java, `malloc` in C).
    
- The stack stores only the **reference (pointer)** to the first node (the head).
    

---

### 🪄 **Types of Linked Lists**

|Type|Structure|Description|
|---|---|---|
|**Singly Linked List**|`Node → Node → Node → NULL`|Each node points only to the next node.|
|**Doubly Linked List**|`NULL ← Node ↔ Node ↔ Node → NULL`|Each node has two pointers: next & prev.|
|**Circular Linked List**|`Node → Node → Node ↺ (back to head)`|Last node points to the first node, forming a loop.|



### 🧮 **Time Complexity Cheat Sheet**

|Operation|Singly Linked List|Doubly Linked List|
|---|---|---|
|Traversal|O(n)|O(n)|
|Search|O(n)|O(n)|
|Insert at beginning|O(1)|O(1)|
|Insert at end|O(n)* (O(1) with tail pointer)|O(n)*|
|Delete from beginning|O(1)|O(1)|
|Delete from end|O(n)*|O(1)* if tail pointer present|

* = depends on whether you maintain a tail pointer.


### 💡 **Advantages**

- Dynamic size (no predefined limit like arrays)
    
- Easy insertion and deletion
    
- Efficient use of memory (no need to shift elements)
    

### ⚠️ **Disadvantages**

- No direct/random access
    
- Extra memory for pointers
    
- Reverse traversal is hard in singly linked lists
    
- More complex to implement


### 🧩 **Linked List vs Array — Comparison Table**

|Feature|Array|Linked List|
|---|---|---|
|Memory|Contiguous|Non-contiguous|
|Access time|O(1) (direct index)|O(n) (traverse)|
|Insertion|O(n)|O(1) (at head)|
|Deletion|O(n)|O(1) (at head)|
|Dynamic size|❌ No|✅ Yes|
|Extra memory|❌ None|✅ Pointer storage|

### 🧠 **Core Terminology**

|Term|Meaning|
|---|---|
|**Node**|Element containing data + pointer|
|**Head**|Pointer to the first node|
|**Tail**|Pointer to the last node|
|**NULL**|Marks the end of the list|
|**Prev**|Pointer to previous node (in doubly list)|


### 🧰 **Internal Workflow Summary**

1. **Node Creation** — Allocate memory dynamically (in heap).
    
2. **Data Assignment** — Store data in the node.
    
3. **Linking Nodes** — Set the “next” pointer of previous node to the address of new node.
    
4. **Traversal** — Start from head and follow next pointers till NULL.
    
5. **Deletion** — Adjust pointers before deleting a node to maintain the chain.
    
6. **Head Update** — Update the head pointer when inserting/deleting at the beginning.
    

---

### 🧾 **Mini Cheat Sheet**

| Concept    | Description                     |
| ---------- | ------------------------------- |
| Node       | `{ data, next }`                |
| Head       | Starting point of list          |
| Tail       | Last node, next = null          |
| Memory     | Heap                            |
| Traversal  | Sequential                      |
| Best for   | Frequent insertions/deletions   |
| Avoid when | Need random access              |
| Complexity | Access O(n), Insert/Delete O(1) |


### 🧠 **Tip for Implementation (JS Example Plan)**

You’ll usually need three parts:

1. **Node class** – defines `data` and `next`.
    
2. **LinkedList class** – maintains `head` and provides methods.
    
3. **Methods to practice** – `insertAtHead`, `insertAtEnd`, `delete`, `search`, `print`.

