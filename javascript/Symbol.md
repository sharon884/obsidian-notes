
## 🔹 1. What is a Symbol?

- A **primitive data type** (like `string`, `number`, etc.) introduced in ES6.
    
- Represents a **unique, immutable identifier**.
    
- Always **different** even if they have the same description.
    

`let id1 = Symbol("id");
let id2 = Symbol("id");

console.log(id1 === id2); // false`

---

## 🔹 2. Symbol Creation

`let sym = Symbol("description"); // optional description console.log(sym.description); // "description"`

✅ Description is only for debugging/logging.

---

## 🔹 3. Symbols as Object Keys

- Symbols can be used as **property keys**.
    
- They don’t clash with string keys.
    

`let user = { name: "Sharon" }; let id = Symbol("id");  user[id] = 123; console.log(user[id]); // 123`

⚡ Property is **hidden from normal `for..in` and `Object.keys()`**.

---

## 🔹 4. Accessing Symbol Keys

`let symbols = Object.getOwnPropertySymbols(user); let allKeys = Reflect.ownKeys(user); // includes symbols + strings`

---

## 🔹 5. Global Symbols (Symbol.for / Symbol.keyFor)

- **Symbol.for(key)** → checks global registry, reuses existing symbol if found.
    
- **Symbol.keyFor(symbol)** → returns the key from the registry.
    

`let s1 = Symbol.for("id");  let s2 = Symbol.for("id"); console.log(s1 === s2); // true  console.log(Symbol.keyFor(s1)); // "id"`

---

## 🔹 6. Well-Known Symbols (Built-in behaviors)

JavaScript defines many built-in symbols that customize object behavior:

|Symbol|Usage|
|---|---|
|`Symbol.iterator`|Makes objects iterable (`for..of`)|
|`Symbol.asyncIterator`|Async iteration|
|`Symbol.toPrimitive`|Custom primitive conversion|
|`Symbol.toStringTag`|Customize `Object.prototype.toString`|
|`Symbol.hasInstance`|Custom `instanceof` behavior|
|`Symbol.isConcatSpreadable`|Control array concat flattening|
|`Symbol.species`|Control constructor in derived objects|
|`Symbol.match`|Custom `str.match` behavior|
|`Symbol.replace`|Custom `str.replace` behavior|
|`Symbol.search`|Custom `str.search` behavior|
|`Symbol.split`|Custom `str.split` behavior|
|`Symbol.unscopables`|Hide properties from `with` environment|

---

## 🔹 7. Example: `Symbol.iterator`

`let range = {   from: 1,   to: 3,   [Symbol.iterator]() {     let current = this.from;     let last = this.to;     return {       next() {         if (current <= last) {           return { value: current++, done: false };         } else {           return { done: true };         }       }     };   } };  for (let num of range) {   console.log(num); // 1, 2, 3 }`

---

## 🔹 8. Example: `Symbol.toPrimitive`

``let user = {   name: "Sharon",   money: 1000,   [Symbol.toPrimitive](hint) {     return hint === "string" ? this.name : this.money;   } };  console.log(+user);      // 1000 console.log(`${user}`);  // "Sharon"``

---

## 🔹 9. Key Points to Remember

- ✅ Symbols are **unique identifiers**.
    
- ✅ Use them to create **hidden object properties**.
    
- ✅ They don’t auto-convert to strings (`alert(sym)` → ❌ TypeError).
    
- ✅ Use `sym.description` if you want a human-readable label.
    
- ✅ For **shared symbols**, use `Symbol.for`.
    
- ✅ For **custom behaviors**, use well-known symbols.
    

---

⚡ **Quick Memory Hook:**

- **Symbol()** → Unique ID
    
- **Symbol.for()** → Global registry
    
- **Well-known symbols** → “Magic hooks” for JS internals