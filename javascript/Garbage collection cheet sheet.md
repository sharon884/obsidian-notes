

## **1. What is Garbage Collection?**

Garbage Collection is the process by which JavaScript **automatically frees up memory** that’s no longer needed by your program.

- In JS, memory is allocated when you create variables, objects, functions, etc.
    
- If something is no longer reachable or used, GC removes it so memory is available for new objects.
    

**Analogy:**  
Think of memory as a room with boxes (objects). When a box is empty and you can no longer reach it, GC comes in and clears it out to make space.

---

## **2. How does JS know what to remove?**

JS uses **“reachability”**:

- **Reachable**: The value can still be accessed somehow (e.g., via a variable or object reference).
    
- **Unreachable**: There’s no reference to it from anywhere in your code → eligible for garbage collection.
    

**Example:**

`let a = { name: "Sharon" }; let b = a; // both a and b point to the same object a = null; // object is still reachable via b b = null; // object is now unreachable → garbage`

---

## **3. Memory Types and Where GC Happens**

1. **Stack Memory**
    
    - Stores primitive values (`number`, `string`, `boolean`) and references to objects.
        
    - Automatic cleanup happens when function execution ends.
        
2. **Heap Memory**
    
    - Stores objects, arrays, functions (non-primitive data).
        
    - GC mainly works here to clean unreachable objects.
        

---

## **4. How JS Garbage Collection Works**

The most common mechanism is **Mark-and-Sweep**:

1. **Mark phase:** JS engine marks all reachable objects.
    
2. **Sweep phase:** Unmarked (unreachable) objects are removed from memory.
    

Other advanced techniques:

- **Reference Counting:** Keeps count of references; removes when count is zero.
    
- **Generational GC:** New objects are checked more frequently; older objects less frequently (optimizes performance).
    

---

## **5. When GC Runs**

- GC runs **automatically**, you can’t force it (except in some special debug modes).
    
- Typically triggered:
    
    - When memory usage grows.
        
    - During idle times to reduce performance impact.
        

---

## **6. Common Patterns That Keep Memory**

- **Global variables:** Always reachable → not collected until program ends.
    
- **Closures:** Variables inside a closure can stay alive if the closure is still referenced.
    
- **DOM references:** Detached DOM elements still referenced in JS won’t be collected.
    

**Tip:** Always set variables to `null` if you no longer need big objects or arrays.

---

## **7. Quick Summary Table**

|Concept|Explanation|
|---|---|
|Reachable|Can be accessed → NOT garbage|
|Unreachable|No references → eligible for GC|
|Stack Memory|Stores primitives, references|
|Heap Memory|Stores objects, functions|
|GC Mechanism|Mark-and-Sweep (main), Reference counting, Generational GC|
|When GC happens|Automatic, engine decides|
|Memory leak examples|Globals, closures, DOM references|

---

✅ **Key Idea:** You don’t manage memory manually in JS. GC automatically removes things you can no longer reach, but being aware of references helps avoid memory leaks.




"In JavaScript, garbage collection is an automatic process that frees up memory occupied by values that are no longer reachable.

- Primitive values stored in the stack, and objects, arrays, or functions stored in the heap, are monitored for reachability.
    
- The engine marks values that are still accessible and removes the ones that are unreachable.
    
- The most common mechanism is mark-and-sweep, but other strategies like reference counting and generational GC also exist.
    
- This ensures that memory used by unused or no-longer-needed data is automatically cleaned up, preventing memory leaks."



## **1. Reachable**

A value is **reachable** if your program can still access it in any way.

- That means there’s at least **one reference** (variable, object property, or closure) pointing to it.
    
- **Reachable values are NOT garbage**—they stay in memory.
    

**Example:**

`let obj = { name: "Sharon" };
let ref = obj; // obj is reachable via both 'obj' and 'ref'`

Here, the object `{ name: "Sharon" }` is **reachable** because both `obj` and `ref` point to it.

---

## **2. Unreachable**

A value is **unreachable** if there are **no references** to it anywhere in the program.

- Once a value is unreachable, the JS engine considers it **garbage** and can remove it from memory.
    

**Example:**

`let obj = { name: "Sharon" };
obj = null; // object is now unreachable`

Now, there’s no variable pointing to the object, so it’s **unreachable** → eligible for garbage collection.

---

### **Analogy**

- Think of objects as items in a warehouse.
    
- **Reachable:** You have the key to open the locker where the item is stored.
    
- **Unreachable:** You lost all keys → no one can access it → it can be thrown away.
    

---

✅ **Key idea:** Garbage collection only removes **unreachable** values. Anything still reachable stays in memory.


![[Pasted image 20250821131220.png]]


# 🗑️ JavaScript Garbage Collection Cheat Sheet

## **1. Memory Basics**

- **Stack Memory**
    
    - Stores **primitive values** (`number`, `string`, `boolean`, `null`, `undefined`, `symbol`, `bigint`)
        
    - Stores **references** (pointers) to objects in heap
        
- **Heap Memory**
    
    - Stores **non-primitives**: objects, arrays, functions, closures, etc.
        

---

## **2. Roots (Entry Points for GC)**

Roots are objects that are always considered **reachable**:

- Global variables (`window` in browsers, `global` in Node.js)
    
- Local variables inside currently running functions
    
- Function parameters
    
- Closures (if still referenced)
    

From these roots, the engine “crawls” through references to find reachable objects.

---

## **3. Reachability**

- **Reachable = Alive** (GC won’t delete)
    
- **Unreachable = Garbage** (GC can remove)
    

🔑 Example:

`let a = { x: 1 };   // reachable via a let b = a;          // also reachable via b a = null;           // still reachable via b b = null;           // now unreachable → GC cleans`

---

## **4. Garbage Collection Methods**

### ✅ **Mark-and-Sweep (Main method)**

1. Start from roots (globals, stack vars).
    
2. **Mark** all reachable objects.
    
3. **Sweep**: delete unmarked (unreachable) objects.
    

---

### ✅ **Reference Counting (older method, rarely used alone)**

- Each object has a counter of references.
    
- When counter → 0 → collected.  
    ⚠️ Problem: can’t handle **circular references**.
    

Example:

`function cycle() {   let a = {};   let b = {};   a.ref = b;   b.ref = a; // circular → ref count never 0 }`

---

### ✅ **Generational GC**

- Objects divided into **young** (new) and **old** (survived longer).
    
- New objects are checked more often (since most die young).
    
- Optimizes performance.
    

---

### ✅ **Incremental & Concurrent GC**

- GC breaks work into **small steps** to avoid blocking main thread.
    
- Concurrent GC runs in parallel with program execution.
    

---

## **5. When Does GC Run?**

- Automatically by JS engine.
    
- Usually during idle time or when memory is low.
    
- You **cannot manually force it** in JS (unlike languages like C++).
    

---

## **6. Memory Leaks (Common Causes)**

- Global variables (never released).
    
- Forgotten timers/intervals (`setInterval` without `clearInterval`).
    
- Detached DOM elements still referenced in JS.
    
- Closures holding large objects.
    

---

## **7. Best Practices**

- Nullify references when no longer needed:
    
    `obj = null;`
    
- Clear timers/listeners:
    
    `clearInterval(id); element.removeEventListener("click", handler);`
    
- Avoid unnecessary globals.
    
- Use **WeakMap / WeakSet** for objects you don’t want to prevent from being garbage collected.
    

---

## **8. Quick Visual Flow**

`Roots (globals, stack, closures)    ↓ Mark phase → mark all reachable    ↓ Unmarked = unreachable    ↓ Sweep phase → memory freed`

---

✅ **One-line Interview Answer:**  
“JavaScript uses automatic garbage collection, mainly the mark-and-sweep algorithm, to free memory. It starts from roots (globals, stack variables, closures), marks all reachable objects, and removes unreachable ones. Optimizations like generational and incremental GC improve performance.”



![[Pasted image 20250821131406.png]]
