
### 🔹 **Definition**

> A **Queue** is a **linear data structure** that follows the **FIFO (First In, First Out)** principle.  
> The element added first is the one removed first.

---

### 🔹 **Basic Concepts**

|Term|Description|
|---|---|
|**Front**|The first element in the queue (to be removed next).|
|**Rear**|The last element in the queue (where new elements are added).|
|**Enqueue**|Operation to **add** an element at the rear.|
|**Dequeue**|Operation to **remove** an element from the front.|
|**Peek / Front**|Get the element at the front without removing it.|
|**isEmpty**|Checks if the queue has no elements.|
|**isFull**|Checks if the queue has reached its maximum capacity (only in fixed-size queues).|

---

### 🔹 **Characteristics**

- Linear data structure (elements arranged sequentially)
    
- Follows **FIFO** order
    
- Has **two ends** → front (deletion) and rear (insertion)
    
- Used for **task scheduling, buffering, and synchronization**
    

---

### 🔹 **Types of Queues**

|Type|Description|
|---|---|
|**Simple Queue**|Insertion at rear, deletion from front (normal FIFO queue).|
|**Circular Queue**|The last position connects back to the first to form a circle; avoids wasted space.|
|**Priority Queue**|Each element has a priority; higher priority elements are dequeued first.|
|**Deque (Double-Ended Queue)**|Insertion and deletion can occur at both ends.|

---

### 🔹 **Real-Life Examples**

- Waiting line at a ticket counter 🎟️
    
- Print queue 🖨️
    
- CPU task scheduling 🧠
    
- Message queue or request handling in servers 🌐
    
- Buffer between devices of different speeds (like CPU & keyboard)
    

---

### 🔹 **Common Operations**

|Operation|Description|Time Complexity|
|---|---|---|
|**Enqueue()**|Add element at rear|O(1)|
|**Dequeue()**|Remove element from front|O(1)|
|**Peek()**|Get element from front without removing|O(1)|
|**isEmpty()**|Check if queue is empty|O(1)|
|**isFull()**|Check if queue is full (in static queues)|O(1)|

---

### 🔹 **Applications**

- **CPU Scheduling**
    
- **Disk Scheduling**
    
- **Data Buffering (IO Buffers)**
    
- **Call center systems**
    
- **Breadth First Search (BFS)** in graphs
    

---

### 🔹 **Example**

`Queue: [10, 20, 30] Front → 10 | Rear → 30 After dequeue() → [20, 30] After enqueue(40) → [20, 30, 40]`