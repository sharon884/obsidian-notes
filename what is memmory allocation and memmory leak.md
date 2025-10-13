
## 🧠 1. What is **Memory Allocation**?

**Memory allocation** means **reserving space in the computer’s memory (RAM)** to store your data when a program runs.

Think of it like this:

> When your program runs, it needs a place in memory to store variables, objects, arrays, or linked lists.  
> The computer “allocates” (gives) that space for your program to use.

---

### 🧩 There are Two Main Types of Memory Allocation:

| Type                   | Description                                                    | Example                                                                                                                                  |
| ---------------------- | -------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Static Allocation**  | Memory is given **at compile time** (before the program runs). | Variables like `int x = 10;` get fixed memory.                                                                                           |
| **Dynamic Allocation** | Memory is given **at runtime** (when the program runs).        | In JavaScript or C, you can create data structures like arrays or linked lists dynamically — they grow or shrink while the program runs. |


---

## 💾 2. How Memory is Divided in a Program

When a program runs, memory is divided into different sections:

| Section                 | What It Stores                                               |
| ----------------------- | ------------------------------------------------------------ |
| **Stack**               | Function calls, local variables (temporary).                 |
| **Heap**                | Dynamically created data like objects, arrays, linked lists. |
| **Code (Text) Section** | The actual program instructions.                             |
| **Data Section**        | Global or static variables.                                  |


## 🧯 3. What is a **Memory Leak**?

A **memory leak** happens when a program **forgets to release unused memory**, even though it’s no longer needed.

That unused memory stays occupied in the **heap**, and over time, your program uses more and more memory until it slows down or crashes.



## 🧰 4. How to Avoid Memory Leaks

|Situation|How to Fix|
|---|---|
|Forgetting to clear references|Set unused variables to `null`|
|Event listeners not removed|Use `removeEventListener()` when not needed|
|Large data stored unnecessarily|Release or overwrite when done|
|Not managing dynamic memory (in C/C++)|Always `free()` or `delete` after use|

---

## ⚙️ 5. Summary

|Concept|Meaning|
|---|---|
|**Memory Allocation**|Reserving memory for storing data.|
|**Dynamic Allocation**|Memory is managed while the program runs.|
|**Memory Leak**|When memory is not released after it’s no longer used.|
|**Why Important**|Leaks can cause apps to slow down or crash over time.|

---