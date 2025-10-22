
A ****monotonic stack**** is a special type of [stack](https://www.geeksforgeeks.org/dsa/stack-data-structure/) data structure where elements are kept in either ****increasing**** or ****decreasing**** order. The main idea is to maintain this order while pushing and popping elements, which helps solve a wide range of problems efficiently.

![Array_.webp](https://media.geeksforgeeks.org/wp-content/uploads/20250915150728714578/Array_.webp)![Array_.webp](https://media.geeksforgeeks.org/wp-content/uploads/20250915150728714578/Array_.webp)
### Understanding Monotonic Stack

A monotonic stack is a stack that maintains its elements in a fixed order either increasing or decreasing.

When a new element is pushed, it is compared with the top of the stack. If the order is violated, elements are popped until the property is restored, and then the new element is pushed.

This way, the stack always stays ordered, and since each element is pushed and popped at most once, the overall operations run in linear time.



## Types of Monotonic Stack:

Monotonic Stacks can be broadly classified into two types:

1. Monotonic Increasing Stack
2. Monotonic Decreasing Stack

### Monotonic Increasing Stack

- Elements inside the stack are always in increasing order.
- While inserting a new element, all greater elements are popped.

Here we can see that at every step, the stack maintains an increasing order from bottom to top.

![Monotonic-Increasing-Stack-3_1.webp](https://media.geeksforgeeks.org/wp-content/uploads/20250905120825449212/Monotonic-Increasing-Stack-3_1.webp)![Monotonic-Increasing-Stack-3_1.webp](https://media.geeksforgeeks.org/wp-content/uploads/20250905120825449212/Monotonic-Increasing-Stack-3_1.webp)



### Monotonic Decreasing Stack

- Elements inside the stack are always in decreasing order.
- While inserting a new element, all smaller elements are popped.


 Here we can see that at every step, the stack maintains a decreasing order from bottom to top.

![Monotonic-Decreasing-Stack-6_1.webp](https://media.geeksforgeeks.org/wp-content/uploads/20250905121034912225/Monotonic-Decreasing-Stack-6_1.webp)![Monotonic-Decreasing-Stack-6_1.webp](https://media.geeksforgeeks.org/wp-content/uploads/20250905121034912225/Monotonic-Decreasing-Stack-6_1.webp)