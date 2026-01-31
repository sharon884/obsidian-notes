A ****Queue Data Structure**** is a fundamental concept in computer science used for storing and managing data in a specific order.

- It follows the principle of "****First in, First out****" ****(FIFO)****, where the first element added to the queue is the first one to be removed.
- It is used as a buffer in computer systems where we have speed mismatch between two devices that communicate with each other. For example, CPU and keyboard and two devices in a network
- Queue is also used in Operating System algorithms like CPU Scheduling and Memory Management, and many standard algorithms like Breadth First Search of Graph, Level Order Traversal of a Tree.

![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20230726165642/Queue-Data-structure1.png)

Queue is a linear data structure that follows ****FIFO**** (First In First Out) Principle, so the first element inserted is the first to be popped out.

****FIFO Principle in Queue:****

FIFO Principle states that the first element added to the Queue will be the first one to be removed or processed. So, Queue is like a line of people waiting to purchase tickets, where the first person in line is the first person served. (i.e. First Come First Serve).

![Dequeue-Operation-in-Queue-1](https://media.geeksforgeeks.org/wp-content/uploads/20250827110558739481/Dequeue-Operation-in-Queue-1.webp)

## Basic Terminologies of Queue

- ****Front:**** Position of the entry in a queue ready to be served, that is, the first entry that will be removed from the queue, is called the front of the queue. It is also referred as the head of the queue.
- ****Rear:**** Position of the last entry in the queue, that is, the one most recently added, is called the rear of the queue. It is also referred as the tail of the queue.
- ****Size:**** Size refers to the current number of elements in the queue.
- ****Capacity:**** Capacity refers to the maximum number of elements the queue can hold.

## ****Types of Queues****

Queue data structure can be classified into 3 types:

![Types-of-Queue](https://media.geeksforgeeks.org/wp-content/uploads/20250917154046246598/Types-of-Queue.webp)

### 1. Simple Queue

A simple queue follows the FIFO (First In, First Out) principle.

- Insertion is allowed only at the rear (back).
- Deletion is allowed only from the front.
- Can be implemented using a linked list or a circular array.

When an array is used, we often prefer a ****circular queue****, which is mainly an efficient array implementation of a simple queue. It efficiently utilizes memory by reusing the empty spaces left after deletion, avoiding wastage that occurs in a normal linear array implementation..

### 2. Double-Ended Queue (Deque)

In a deque, insertion and deletion can be performed from both ends.

### 3. Priority Queue

A queue where each element is assigned a ****priority****, and deletion always happens based on priority (not just position).

## Queue Operations

1. ****Enqueue****: Adds an element to the end (rear) of the queue. If the queue is full, an overflow error occurs.
2. ****Dequeue****: Removes the element from the front of the queue. If the queue is empty, an underflow error occurs.
3. ****Peek/Front****: Returns the element at the front without removing it.
4. ****Size****: Returns the number of elements in the queue.
5. ****isEmpty****: Returns true if the queue is empty, otherwise false.
6. ****isFull****: Returns true if the queue is full, otherwise false.

For detailed steps and more information on each operation, Read [Basic Operations for Queue in Data Structure](https://www.geeksforgeeks.org/dsa/basic-operations-for-queue-in-data-structure/).

## Implementation of Queue

Queue can be implemented using following data structures:

- [Simple Array implementation of Queue](https://www.geeksforgeeks.org/dsa/array-implementation-of-queue-simple/)
- [Efficient Array Implementation of Queue](https://www.geeksforgeeks.org/dsa/introduction-to-circular-queue/)
- [Implementation of Queue using Linked List](https://www.geeksforgeeks.org/dsa/queue-linked-list-implementation/)

### Application of Queue

![Applications-of-Queue](https://media.geeksforgeeks.org/wp-content/uploads/20250917152239558345/Applications-of-Queue.webp)

### Advantages of Queue

![Advantages-of-Queue](https://media.geeksforgeeks.org/wp-content/uploads/20250917152106069252/Advantages-of-Queue.webp)


node js asychchnous task hadling the queue also an example for the queue using applications 
