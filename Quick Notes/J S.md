

**ES6 / ES2015** → `let`, `const`, arrow functions, classes, promises, template literals


> **ECMAScript is the official specification that defines how JavaScript should work. JavaScript is the implementation of that specification, and JavaScript engines like V8 implement the ECMAScript standard so the language behaves consistently across different environments.**

### One-line trick to remember

- **ECMAScript = Rules (Specification)**
- **JavaScript = Language**
- **V8 = Engine that implements those rules**
- **Browser/Node.js = Runtime that provides the environment to execute JavaScript**


## What is a Runtime?

**Runtime is the environment where your code actually executes.**

 


> JavaScript is neither a purely compiled language nor a purely interpreted language. Modern JavaScript engines like V8 use **Just-In-Time (JIT) compilation**. V8 first parses the source code, creates an AST, and uses **Ignition** to generate bytecode and begin execution. If some code is executed frequently (hot code), **TurboFan** compiles it into optimized machine code. This provides both fast startup and high performance.



> **Web APIs are APIs provided by the browser runtime that allow JavaScript to perform operations such as timers, DOM manipulation, network requests, storage, and geolocation. They are not part of the JavaScript language itself and are executed by the browser, not by the V8 engine.**



# What is Dynamic Typing?

**Dynamic typing means you don't need to declare the data type of a variable. JavaScript determines the type automatically at runtime.**

JavaScript is a dynamically typed language, meaning you don't explicitly declare variable types. The JavaScript engine determines the type at runtime, and a variable can hold values of different data types during its lifetime.




JavaScript data types are divided into two categories: primitive and non-primitive. Primitive types include Number, String, Boolean, Undefined, Null, Symbol, and BigInt. They store actual values and are copied by value. Non-primitive types, such as Objects, Arrays, and Functions, store references to objects in memory and are copied by reference.

"Primitive values are copied by value, so each variable has its own independent value. Non-primitive values such as objects and arrays are copied by reference. Conceptually, the object exists separately in memory, and variables hold a reference to it. When two variables reference the same object, changes made through one variable are visible through the other. Although people often describe this as stack and heap memory, those are implementation details of JavaScript engines like V8 rather than requirements of the ECMAScript specification."



# Falsy Values

JavaScript has only **8 falsy values**.

```
false
0
-0
0n
""      // Empty string
null
undefined
NaN
```


# Truthy Values

Everything **other than those 8 values** is truthy.

Examples:

```
1
-1
"Hello"
"0"
"false"
[]
{}
function(){}
42n
```


# Undefined

**`undefined` means a variable has been declared but has not been assigned a value yet.**

# Null

**`null` means the value is intentionally empty.**

# What is Type Coercion?

**Type coercion is the automatic or explicit conversion of one data type to another.**

There are **2 types**:

1. **Implicit Type Coercion** (Automatic)
2. **Explicit Type Conversion** (Manual)
Type coercion is the automatic conversion of one data type to another by JavaScript when an operation requires compatible types. For example, `+` may convert values to strings for concatenation, while operators like `-`, `*`, and `/` usually convert values to numbers. Developers can also perform explicit type conversion using functions such as `Number()`, `String()`, and `Boolean()`.


# What is a Prototype?

A **prototype is another object that JavaScript uses as a backup** when the current object doesn't contain the property or method you're trying to access.
A prototype is an object linked to another object. When a property or method is not found on the object itself, JavaScript automatically searches for it in the object's prototype. This mechanism enables inheritance and allows multiple objects to share methods efficiently, reducing memory usage.


The prototype chain is JavaScript's mechanism for property lookup. When a property or method isn't found on an object, JavaScript checks the object's prototype. If it's still not found, it continues checking each prototype in the chain until it either finds the property or reaches `null`, which marks the end of the chain.


### Constructor Function

> A constructor function is a regular JavaScript function intended to create and initialize multiple objects with the same structure. When called with the `new` keyword, it creates a new object, initializes it through `this`, links it to the constructor's prototype, and returns it.

### `new` Keyword

> The `new` keyword creates a new object, links it to the constructor's prototype, binds `this` to that new object, executes the constructor function, and automatically returns the created object (unless the constructor explicitly returns another object).

---

### `this`

> `this` is a special keyword whose value depends on **how a function is invoked**. It does not belong to the function itself. In a constructor called with `new`, `this` refers to the newly created object.

---



Both constructor functions and classes use the same underlying idea. Instead of manually creating multiple objects with the same structure, we create a blueprint. We then use the `new` keyword to create a new object from that blueprint. During object creation, the constructor function (or the `constructor` method in a class) initializes the object's properties using `this`. The `new` keyword creates the new object, links it to the constructor's prototype, binds `this` to the newly created object, executes the constructor, and finally returns the object.


> **"Why do JavaScript classes use prototypes?"**

A strong answer would be:

> "JavaScript uses prototypes to share methods among all instances of a constructor or class. Instead of creating a separate copy of each method for every object, methods are stored once on the constructor's prototype. When an instance calls a method, JavaScript first checks the instance itself, and if the method isn't found, it follows the prototype chain to the constructor's prototype. This reduces memory usage and enables inheritance."


"In session authentication, after a successful login the server creates a session and stores the user's data on the server. The browser stores only a session ID in a cookie, and each request includes that ID so the server can retrieve the session. In JWT authentication, the server generates a signed token containing user claims and sends it to the client. The client sends the token with future requests, and the server validates the token's signature instead of looking up session state. Sessions are stateful because the server stores user state, while JWT authentication is stateless because the server doesn't need to maintain per-user session data."