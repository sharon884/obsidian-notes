

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