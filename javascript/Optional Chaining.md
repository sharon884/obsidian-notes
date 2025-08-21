
?.

### 🔹 What it is

- A **safe way** to access nested object properties/methods.
    
- Prevents runtime errors if something is **`null`** or **`undefined`**.
    
- Returns **`undefined`** instead of throwing an error.
    

---

### 🔹 Why we need it

`let user = {}; 

console.log(user.address.street); // ❌ Error (address is undefined) 

console.log(user?.address?.street); // ✅ undefined (no error)`

---

### 🔹 Syntax Forms

1. **Property Access**
    

`obj?.prop     // instead of obj.prop`

2. **Bracket Access**
    

`obj?.[prop]   // instead of obj[prop]`

3. **Method/Function Call**
    

`obj.method?.()   // calls if method exists`

---

### 🔹 Examples

#### 1. Property Access

`let user = null;

console.log(user?.address); // undefined 

console.log(user?.address?.street); // undefined`

#### 2. Bracket Notation

`let key = "firstName";

let user1 = { firstName: "John" };

let user2 = null;  

console.log(user1?.[key]); // "John"

console.log(user2?.[key]); // undefined`

#### 3. Method Call

`let userAdmin = {   admin() { console.log("I am admin"); } };

let userGuest = {};

userAdmin.admin?.(); // "I am admin"

userGuest.admin?.(); // nothing (safe)`

---

### 🔹 Short-circuiting

Stops immediately if left side is null/undefined.

`let user = null; 

let x = 0;  

user?.sayHi(x++); // ❌ not executed 

console.log(x);   // 0`


---

### 🔹 With `delete`

`delete user?.name; // deletes user.name if user exists`

---

### 🔹 ❌ Not Allowed on Assignment

`let user = null; 

user?.name = "John"; 

// Error (invalid left-hand side)`

---

### 🔹 Good Practices

✅ Use `?.` only when it’s **valid for something to be missing**.  
❌ Don’t overuse — might hide programming errors.

---

### 🔹 Summary

- `obj?.prop` → safe property access.
    
- `obj?.[prop]` → safe bracket notation.
    
- `obj.method?.()` → safe method call.
    
- Returns **`undefined`** if left side is `null`/`undefined`.
    
- **Stops execution** (short-circuits) if value doesn’t exist.
    
- Doesn’t work on assignment (`user?.name = "x"`).
    

---

👉 **One-liner definition:**  
**Optional chaining = "Stop and return `undefined` if the thing before me is `null` or `undefined`, otherwise continue."**