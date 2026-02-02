

<h1> any vs unknown </h1>


> **`any` turns OFF TypeScript’s type checking.**

`let value: any; 

value = 10; 

value = "hello";

value.toUpperCase(); // ✅ allowed (no check)`

- No type safety
    
- No compiler errors
    
- Can cause runtime crashes
    

    

---

###  `unknown`

> **`unknown` is a safe version of `any`.**

`let value: unknown;

value = 10; 

value = "hello"; 

value.toUpperCase(); // ❌ Error`

TypeScript forces you to **check the type first**.

---

## How to Use `unknown` Safely

`if (typeof value === "string") {  

value.toUpperCase(); // ✅ safe

}`

Or with custom type guards.

---

## Key Differences Table 

|Feature|`any`|`unknown`|
|---|---|---|
|Type safety|❌ None|✅ High|
|Type checking|Disabled|Enforced|
|Method access|Allowed|❌ Must check|
|Runtime safety|Low|High|
|Recommended|❌ Avoid|✅ Prefer|

---

## When to Use Each

### Use `any`

- Migrating old JS code
    
- Quick prototypes
    
- Temporary workaround
    

### Use `unknown`


- API responses
    
- `try/catch` errors
    
- User input
    
- External data