

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