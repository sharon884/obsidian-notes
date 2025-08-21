

## **1️⃣ Primitive vs Non-Primitive**

| Feature          | Primitive Values                                         | Non-Primitive (Objects)                             |
| ---------------- | -------------------------------------------------------- | --------------------------------------------------- |
| Types            | Number, String, Boolean, Null, Undefined, Symbol, BigInt | Object, Array, Function                             |
| Stored in memory | **Stack** (value stored directly)                        | **Heap** (object stored, variable stores reference) |
| Assignment       | **Pass by value**                                        | **Pass by reference**                               |
| Example          | `let a = 10; let b = a; b=20; a=10`                      | `let obj = {x:1}; let obj2=obj; obj2.x=2; obj.x=2`  |

## **2️⃣ Stack Memory vs Heap Memory**

| Feature           | Stack                         | Heap                          |
| ----------------- | ----------------------------- | ----------------------------- |
| Stores            | Primitive values & references | Objects, arrays, functions    |
| Access            | Fast                          | Slightly slower               |
| Size              | Small                         | Large                         |
| Memory management | Auto (LIFO)                   | Garbage collection            |
| Example           | `let a = 10;`                 | `let user = {name:"Sharon"};` |


**3️⃣ Object Assignment & References**

![[Pasted image 20250821122608.png]]

- **Explanation:** Both variables point to **same object in heap** → changes affect both.
    
- ✅ This is **pass by reference**.


## **4️⃣ Shallow Copy**

- Copies **only top-level properties**.
    
- Nested objects/arrays **still share references**.
    

### **Using `Object.assign()`**


![[Pasted image 20250821122705.png]]
## **5️⃣ Deep Copy**

- Copies **all levels**, nested objects/arrays are independent.
    
- Methods:


![[Pasted image 20250821122759.png]]

**6️⃣ Summary Table: Copy Types

| Copy Type      | What it copies       | Nested objects | Example                                                    |
| -------------- | -------------------- | -------------- | ---------------------------------------------------------- |
| Reference copy | Reference only       | Shared         | `let a=obj;`                                               |
| Shallow copy   | Top-level properties | Shared         | `Object.assign({}, obj)` / `{...obj}`                      |
| Deep copy      | All levels           | Independent    | `structuredClone(obj)` / `JSON.parse(JSON.stringify(obj))` |


![[Pasted image 20250821122906.png]]

## **8️⃣ Quick Tips**

1. Primitive = stored **by value** → independent.
    
2. Object = stored **by reference** → changes reflect in all references.
    
3. `Object.assign` & spread operator → **shallow copy**.
    
4. `structuredClone` → **deep copy**, fully independent.
    
5. Nested objects always need **deep copy** if you want independent changes.
    
6. Stack = fast, fixed, for primitives & references.
    
7. Heap = large, dynamic, for objects, arrays, functions.

![[Pasted image 20250821123044.png]]


![[Pasted image 20250821123110.png]]




