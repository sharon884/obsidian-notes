
A function that is a property of an object is called its _method_.


## [“this” in methods](https://javascript.info/object-methods#this-in-methods)


It’s common that an object method needs to access the information stored in the object to do its job.

For instance, the code inside `user.sayHi()` may need the name of the `user`.

**To access the object, a method can use the `this` keyword.**

The value of `this` is the object “before dot”, the one used to call the method.

For instance:

[](https://javascript.info/object-methods# "run")

[](https://javascript.info/object-methods# "open in sandbox")

```javascript
let user = {
  name: "John",
  age: 30,

  sayHi() {
    // "this" is the "current object"
    alert(this.name);
  }

};

user.sayHi(); // John
```

Here during the execution of `user.sayHi()`, the value of `this` will be `user`.

Technically, it’s also possible to access the object without `this`, by referencing it via the outer variable:

```javascript
let user = {
  name: "John",
  age: 30,

  sayHi() {
    alert(user.name); // "user" instead of "this"
  }

};
```

…But such code is unreliable. If we decide to copy `user` to another variable, e.g. `admin = user` and overwrite `user` with something else, then it will access the wrong object.

That’s demonstrated below:

[](https://javascript.info/object-methods# "run")

[](https://javascript.info/object-methods# "open in sandbox")

```javascript
let user = {
  name: "John",
  age: 30,

  sayHi() {
    alert( user.name ); // leads to an error
  }

};


let admin = user;
user = null; // overwrite to make things obvious

admin.sayHi(); // TypeError: Cannot read property 'name' of null
```

If we used `this.name` instead of `user.name` inside the `alert`, then the code would work.


## [“this” is not bound](https://javascript.info/object-methods#this-is-not-bound)

In JavaScript, keyword `this` behaves unlike most other programming languages. It can be used in any function, even if it’s not a method of an object.

There’s no syntax error in the following example:

```javascript
function sayHi() {
  alert( this.name );
}
```

The value of `this` is evaluated during the run-time, depending on the context.

For instance, here the same function is assigned to two different objects and has different “this” in the calls:

[](https://javascript.info/object-methods# "run")

[](https://javascript.info/object-methods# "open in sandbox")

```javascript
let user = { name: "John" };
let admin = { name: "Admin" };

function sayHi() {
  alert( this.name );
}

// use the same function in two objects
user.f = sayHi;
admin.f = sayHi;

// these calls have different this
// "this" inside the function is the object "before the dot"
user.f(); // John  (this == user)
admin.f(); // Admin  (this == admin)

admin['f'](); // Admin (dot or square brackets access the method – doesn't matter)
```

The rule is simple: if `obj.f()` is called, then `this` is `obj` during the call of `f`. So it’s either `user` or `admin` in the example above.

Calling without an object: `this == undefined`

We can even call the function without an object at all:

[](https://javascript.info/object-methods# "run")

[](https://javascript.info/object-methods# "open in sandbox")

```javascript
function sayHi() {
  alert(this);
}

sayHi(); // undefined
```

In this case `this` is `undefined` in strict mode. If we try to access `this.name`, there will be an error.

In non-strict mode the value of `this` in such case will be the _global object_ (`window` in a browser, we’ll get to it later in the chapter [Global object](https://javascript.info/global-object)). This is a historical behavior that `"use strict"` fixes.

Usually such call is a programming error. If there’s `this` inside a function, it expects to be called in an object context.

The consequences of unbound `this`

If you come from another programming language, then you are probably used to the idea of a “bound `this`”, where methods defined in an object always have `this` referencing that object.

In JavaScript `this` is “free”, its value is evaluated at call-time and does not depend on where the method was declared, but rather on what object is “before the dot”.

The concept of run-time evaluated `this` has both pluses and minuses. On the one hand, a function can be reused for different objects. On the other hand, the greater flexibility creates more possibilities for mistakes.

Here our position is not to judge whether this language design decision is good or bad. We’ll understand how to work with it, how to get benefits and avoid problems.

## [Arrow functions have no “this”](https://javascript.info/object-methods#arrow-functions-have-no-this)

Arrow functions are special: they don’t have their “own” `this`. If we reference `this` from such a function, it’s taken from the outer “normal” function.

For instance, here `arrow()` uses `this` from the outer `user.sayHi()` method:

[](https://javascript.info/object-methods# "run")

[](https://javascript.info/object-methods# "open in sandbox")

```javascript
let user = {
  firstName: "Ilya",
  sayHi() {
    let arrow = () => alert(this.firstName);
    arrow();
  }
};

user.sayHi(); // Ilya
```

That’s a special feature of arrow functions, it’s useful when we actually do not want to have a separate `this`, but rather to take it from the outer context. Later in the chapter [Arrow functions revisited](https://javascript.info/arrow-functions) we’ll go more deeply into arrow functions.

## [Summary](https://javascript.info/object-methods#summary)

- Functions that are stored in object properties are called “methods”.
- Methods allow objects to “act” like `object.doSomething()`.
- Methods can reference the object as `this`.

The value of `this` is defined at run-time.

- When a function is declared, it may use `this`, but that `this` has no value until the function is called.
- A function can be copied between objects.
- When a function is called in the “method” syntax: `object.method()`, the value of `this` during the call is `object`.


## **1. What is `this`?**

- `this` is a **special keyword** whose value depends on **how a function is called**, not where it’s written.
    
- It gives a function a way to access the object that “owns” it at runtime.



## **4. Summary Table**

|Context|Value of `this`|
|---|---|
|Function (non-strict)|`global` (window/global)|
|Function (strict)|`undefined`|
|Method of object|Object before dot|
|Arrow function|Lexical (outer scope)|
|Constructor / Class|New instance|
|`call`, `apply`, `bind`|Explicitly set|
|setTimeout normal func|Global/undefined|
|setTimeout arrow func|Outer scope|

---

## **5. Interview One-liner**

> "`this` in JavaScript is dynamically bound depending on how a function is called. In object methods it refers to the object, in constructors it refers to the new instance, in global functions it’s global/undefined, and arrow functions inherit `this` from their surrounding scope. You can also explicitly control it using `call`, `apply`, or `bind`."



👉 **`this` is available everywhere in JavaScript, not just inside functions** — but its value depends on **where and how** you use it.


## **1. Global Scope**

- In the **global scope** (outside of any function):
    
    - In browsers: `this === window`
        
    - In Node.js: `this === {}` (an empty object in modules)



## **2. Inside a Function**

- In **non-strict mode**: `this = global` (`window` in browser)
    
- In **strict mode**: `this = undefined`
    

`function show() {   console.log(this); } show(); // window`



## **3. Inside Object Methods**

Here `this` points to the object before the dot:

`const user = {   name: "Sharon", 
greet() {     console.log(this.name);   } }; 
user.greet(); // Sharon

## **4. Inside Classes / Constructors**

When used with `new`, `this` points to the newly created object:

`class Person {   constructor(name) {     this.name = name;   } }
const p = new Person("Sharon");
console.log(p.name); // Sharon``


## **5. Inside Arrow Functions**

Arrow functions don’t have their own `this` → they inherit it from the **outer scope**.

`const obj = {   name: "Sharon", 
arrow: () => console.log(this.name) };
obj.arrow();  // undefined (because outer scope is global, not obj);


- `this` is **not limited to functions**.
    
- It exists in the global scope, inside functions, methods, classes, arrow functions, and even with `call`, `apply`, `bind`.
    
- But in practice, it’s most _useful_ inside **functions and methods**, because that’s where we need access to the object context.
- 
- 
- `
