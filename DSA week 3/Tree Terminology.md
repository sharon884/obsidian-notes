

- **Subtree** → Any node and its descendants form a smaller tree.
    
- **Ancestor** → All nodes on the path from the root to a specific node (excluding the node itself).
    
- **Descendant** → All nodes that come under a particular node (children, grandchildren, etc.).
    
- **Height of Tree** → Longest path from the root to a leaf node.
    
- **Depth of a Node** → Distance (number of edges) from the root to that node.
    
- **Degree of a Node** → Number of direct children that a node has.
    
- **Sibling** → Nodes that share the same parent.



#### 1️⃣ **Ancestor**

If you move **upward** from a node (toward the root),  
every node you encounter is an **ancestor** of that node.

Example:

        `A   
        
        / \     
        
	    B   C   
	   
		/ \   
	    
	     D   E`

- Ancestors of **E** = {B, A}
    
- Ancestors of **D** = {B, A}
    

💡 In simple words: _Ancestors = all parents, grandparents, etc., up to the root._

---

#### 2️⃣ **Descendant**

If you move **downward** from a node,  
every node below it is a **descendant**.

Example:

- Descendants of **A** = {B, C, D, E}
    
- Descendants of **B** = {D, E}
    

💡 Think of it as “children, grandchildren, great-grandchildren…”

---

#### 3️⃣ **Height vs Depth**

- **Height of a node** = the **longest path** from that node **down to a leaf**
    
- **Depth of a node** = the **distance from the root** to that node
    

Example:

        `A       
        
		 / \     
		 
		B   C   
	     
	    / \  
	 
		D   E`

|Node|Depth|Height|
|---|---|---|
|A|0|2|
|B|1|1|
|D|2|0|
|E|2|0|

💡 **Root depth = 0**, **Leaf height = 0**.

---

#### 4️⃣ **Level**

Level = Depth + 1  
So:

- Root → level 1
    
- Its children → level 2
    
- Their children → level 3  
    ... and so on.
    

---

#### 5️⃣ **Subtree**

Any node and _all its descendants_ form a subtree.  
Example:  
If we take node **B** from the above example —  
the subtree is:

     `B     / \    D   E`

---

### 💡 Quick Summary Table

|Term|Direction|Meaning|
|---|---|---|
|**Ancestor**|Upward|Parents, grandparents, etc.|
|**Descendant**|Downward|Children, grandchildren, etc.|
|**Depth**|From root → node|Distance to root|
|**Height**|From node → leaf|Longest path down|
|**Level**|Depth + 1|Node’s vertical position|
|**Subtree**|—|Node + its descendants|