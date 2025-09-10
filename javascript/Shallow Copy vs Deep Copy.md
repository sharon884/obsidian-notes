

**Shallow Copy:**  
A **shallow copy** only copies the **top-level properties** of an object.  
If the object contains **nested objects or arrays**, the copy only stores the **reference** to those nested structures.  
So, if we modify a nested object in the copy, the change will also reflect in the original.

👉 In JavaScript, methods like the **spread operator (`{...obj}`)** or `Object.assign()` create shallow copies.



**Deep Copy:**  
A **deep copy** creates a **fully independent clone** of the object, including all nested objects and arrays.  
The copied object does **not share references** with the original.  
So, modifying nested properties in the copy does **not affect** the original.

👉 In JavaScript, we can use **`JSON.parse(JSON.stringify(obj))`** (simple case) or the modern **`structuredClone()`** method to create a deep copy.


