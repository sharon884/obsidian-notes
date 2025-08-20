
## [Function Declaration](https://javascript.info/function-basics#function-declaration)


## 1. Function Declaration

- Defined with the `function` keyword.
    
- Can be called **before** they are defined (hoisting).
    

`function sayHi(name) {   return "Hi " + name; } 
console.log(sayHi("Sharon")); // "Hi Sharon"`

✅ Hoisted  
✅ Has its own name  
✅ Good for reusable functions

---

## 2. Function Expression

- A function stored in a variable.
    
- Not hoisted (must be defined before use).
    

`let sayHi = function(name) {   return "Hi " + name; };  
console.log(sayHi("Sharon")); // "Hi Sharon"`

👉 Often **anonymous** (no name after `function`)  
👉 Can also be **named function expression**:

`let sayHi = function greet(name) {   return "Hi " + name; };`

---

## 3. Arrow Functions

- Shorter syntax for writing function expressions.
    
- Always **anonymous**.
    
- Do **not** have their own `this`, `arguments`, or `super`.
    

`let sum = (a, b) => a + b;  let sayHi = () => console.log("Hello!");`

✔️ Great for callbacks and small functions  
❌ Not suitable when `this` is needed (e.g., in object methods)

---

## 4. Returning Values

`function add(a, b) {   return a + b; }
let multiply = (a, b) => a * b;  
console.log(add(2,3));      // 5 console.log(multiply(2,3)); // 6`

If no `return` → returns `undefined`.

---

## 5. Parameters & Defaults

`function greet(name = "Guest") {   console.log("Hello, " + name); } 
greet();     
// Hello, Guest
greet("Sharon");
// Hello, Sharon`

---

## 6. Callback Functions

Functions can be passed as arguments.

`function ask(question, yes, no) {   if (confirm(question)) yes();   else no(); }  ask(   "Do you agree?",   () => alert("You agreed."),   () => alert("You canceled.") );`

---

## 7. Function as a Value

Functions are objects → can be stored, passed, returned.

`function makeMultiplier(factor) {   return function(number) {     return number * factor;   }; }  let double = makeMultiplier(2); console.log(double(5)); // 10`

---

## 8. Differences ⚡

|Feature|Function Declaration|Function Expression|Arrow Function|
|---|---|---|---|
|**Hoisting**|✅ Yes|❌ No|❌ No|
|**Name**|Has a name|Can be anonymous or named|Always anonymous|
|**this**|Own `this`|Own `this`|Inherits from outer scope|
|**Syntax**|`function f() {}`|`let f = function() {}`|`let f = () => {}`|