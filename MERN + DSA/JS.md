Js concepts 


# Master JavaScript Concepts (Complete + Clean + Merged)

Below is the unified, non-duplicate, fully organized list of **all JavaScript concepts** based on:

* Concepts you provided
* Pending lists from your DOCX
* Missing concepts required for MERN interviews
* Essential fundamentals → advanced

---

# 1. **JavaScript Fundamentals**

* Synchronous vs Asynchronous
* Single-thread vs Multi-thread (JS is single-threaded; browser/Node provide async capabilities)
* Dynamically typed vs Statically typed (JS vs TS)
* Primitives vs Non-primitives
* Pass by value vs Pass by reference
* Undefined vs Null
* Truthy vs Falsy
* NaN (Not-a-Number)
* Operator precedence
* Conditional (ternary) operator
* Nullish coalescing operator (??)
* Optional chaining (?.)
* Type casting vs Type coercion
* Boolean coercion (!!)
* typeof
* isArray

---

# 2. **Variables & Scope**

* let, var, const
* Hoisting
* Temporal Dead Zone (TDZ)
* Global Execution Context (GEC)
* Scope: Global, Function, Block
* Scope chain
* Variable shadowing
* Illegal shadowing
* use strict
* Named parameters
* Value of let/const inside TDZ

---

# 3. **Functions**

* Function declaration vs function expression
* Arrow function vs Regular function
* Arrow functions and hoisting
* Arrow function "this" behavior
* Regular function "this" binding
* IIFE (Immediately Invoked Function Expression)
* Factory function
* Constructor function
* Pure vs Impure functions
* First-class functions
* Higher Order Functions (HOF)
* Callback functions
* Callback hell
* Currying
* Partial application
* Function composition
* Eval()
* Generator function
* (Task) Generator to produce even numbers endlessly

---

# 4. **Advanced Function Concepts**

* Closures
* Applications of closures
* Limitations of closures
* Closure + Garbage collection
* Named vs anonymous
* Arguments object
* Rest parameters
* Spread operator
* Polyfills (map, filter, reduce, bind, call, apply)
* Function borrowing (call, apply, bind)

---

# 5. **Objects & Prototype System**

* Object creation: literal, constructor, Object.create
* this keyword
* Prototype
* **proto** vs prototype
* Prototype chain
* Prototypal inheritance
* Classical inheritance (ES6 classes)
* Object.defineProperty()
* Object.freeze
* Deep freeze
* WeakMap / WeakSet
* Map / Set
* WeakRef
* Proxy
* Proxy traps
* Symbol type
* Private fields in classes (#value)
* Extends keyword
* Factory vs constructor vs class
* Jagged array

---

# 6. **Arrays & Strings**

### **Array Concepts**

* Homogeneous vs Heterogeneous arrays
* Sparse arrays
* Array methods: map, filter, reduce, forEach, some, every, find, findIndex, flat, flatMap
* Using reduce for problems (largest odd number, grouping, etc.)
* Removing duplicates
* Practical array problems

### **String Concepts**

* String methods: slice, substring, split, trim, replace, includes
* String reversal
* Count characters using a hashtable
* Palindromic substrings

---

# 7. **Execution & Internal Working**

* JavaScript Engine (V8)
* Parsing → AST → Bytecode → Execution
* Interpreter vs Compiler
* JIT (Just-In-Time compilation)
* Baseline interpreter (Ignition)
* Optimizing compiler (TurboFan)
* Call stack
* Memory heap
* Execution context
* Event loop
* Web APIs
* Microtask queue
* Macrotask queue
* Phases in event loop
* Starvation
* Blocking vs Non-blocking code

---

# 8. **Asynchronous Programming**

* setTimeout, setInterval
* Ajax
* Fetch
* Promise
* Promise states
* Promise chaining
* Promise methods:

  * Promise.all
  * Promise.allSettled
  * Promise.race
  * Promise.any
* Async/await
* Error handling in promises
* Promisify
* Cancel token (Axios)
* Axios interceptors
* Preflight request (CORS)
* OPTIONS method
* Idempotency (PUT vs POST)

---

# 9. **DOM & Browser Concepts**

* DOM tree
* querySelector / getElementById
* appendChild, createElement
* Event listeners
* Event propagation
* Event capturing
* Event bubbling
* Event delegation
* Event flow in JS
* Event pooling (React)
* Shadow DOM
* HTML sanitization
* Blocking code in browser

---

# 10. **Error Handling**

* Try–catch
* Finally
* Custom errors
* Null pointer exception

---

# 11. **Design Patterns (JS Focused)**

* Factory pattern
* Singleton pattern
* Module pattern
* Observer pattern
* Strategy pattern
* Iterator pattern (generators)

---

# 12. **Streams, Buffer, Memory**

* Buffer in Node.js
* Stream types: Readable, Writable, Duplex, Transform
* Piping
* Transform vs Duplex
* Create piping using stream

---

# 13. **Node.js (JS-Specific Concepts Only)**

* Node.js architecture
* Event-driven programming
* Event emitters
* Process vs Thread
* Thread pool
* Worker threads
* Cluster vs Worker thread
* Dynamic routing (req.params)
* Router chaining
* Error-first callback
* fs operations
* buffer class
* npm init

---

# 14. **Security & HTTP (JS-relevant)**

* CSRF
* CORS
* Headers
* Cookies:

  * httpOnly
  * sameSite
  * secure
  * domain rules
* Content negotiation
* API versioning
* REST principles
* HTTP status codes (1xx–5xx)
* Fetch vs Axios

---

# 15. **Data Structures Implemented with JS**

* Reverse string using recursion
* Balanced parentheses using stack
* Monotonic stack
* Monotonic queue
* Queue problems
* Hash table implementation
* Applications of heap
* Detect cycle in graph
* BFS & DFS complexity
* Implement Trie
* Implement Graph (Adj list)
* Degenerate tree
* Complete tree
* Full binary tree
* Hash table resizing
* Quadratic probing

---

# 16. **Special Practical Problems (JS Version)**

* Print patterns using loops & generators
* Remove duplicates from array
* Remove properties from object
* Check if object is empty
* Make an object immutable
* Swap middle elements of a queue
* 2*2*2 pattern generator
* Sorting + reduce tasks

---

# 17. **Miscellaneous JS Concepts**

* JSON.parse / JSON.stringify
* Boolean coercion
* Escape sequences
* Debugger
* Pipeline operator (proposed)
* Alternative for IIFE
* Sparse vs dense array behavior
* Object.assign uses

---

End of document.
