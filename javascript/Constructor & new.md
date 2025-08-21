
### 🔹 Constructor Functions

- Regular functions, but **meant to create objects**.
    
- **Naming rule** → Start with **Capital Letter**.
    
- Always called with **`new` operator**.
    

`function User(name)
{   this.name = name;   this.isAdmin = false; } 
let user = new User("Jack"); 
// creates { name: "Jack", isAdmin: false }`

---

### 🔹 What happens when you call with `new`:

1. A new empty object `{}` is created.
    
2. `this` inside the function refers to that object.
    
3. Function body executes → properties/methods are added to `this`.
    
4. `this` is returned (unless an object is returned manually).
    

---

### 🔹 Equivalent without `new`

`let user = new User("Jack"); 
// Same as let user = {   name: "Jack",   isAdmin: false };`

---

### 🔹 `new function() { … }`

- Creates and immediately executes a constructor → **one-time object**.
    

`let user = new function() 
{   this.name = "John";   this.isAdmin = false; };`

---

### 🔹 `new.target`

- Inside a function → tells if it was called with `new`.
    

`` function User(name)
{   if (!new.target) return new User(name); // auto-adds `new`   this.name = name; } 
let john = User("John");   // works even without `new` ``

---

### 🔹 `return` in Constructors

- If **return object** → overrides `this`.
    
- If **return primitive / nothing** → ignored, returns `this`.
    

`function BigUser() {   this.name = "John";   return { name: "Godzilla" };  } new BigUser().name; // "Godzilla"  function SmallUser() {   this.name = "John";   return;  } new SmallUser().name; // "John"`

---

### 🔹 Omitting Parentheses

`let user = new User;   // same as new User()`

⚠️ Allowed, but **bad style**.

---

### 🔹 Methods inside Constructor

- You can attach methods directly.
    

`function User(name) {   this.name = name;   this.sayHi = function() {     console.log("My name is " + this.name);   }; } 
let john = new User("John"); john.sayHi(); // My name is John`

---

### ✅ Summary

- Constructor functions = reusable object creation templates.
    
- Must be called with `new`.
    
- `new` automatically handles creating and returning the object.
    
- `return` only matters if it’s an **object**.
    
- You can add properties + methods in constructors.
    
- Use **capitalized names** for constructors.