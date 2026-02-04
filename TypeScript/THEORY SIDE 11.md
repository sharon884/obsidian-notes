
<h1> Literal Types  </h1>

Literal = **exact value allowed**


Union types allow a variable to hold multiple possible types, whereas literal types restrict a variable to specific exact values. Literal types are often combined using unions to strictly control allowed values.



Union types allow a variable to have multiple **types** like string or number.  
Literal types allow only **exact predefined values**, and when we want a variable to accept only specific values without errors, we use literal types (often combined using unions).



### Union Types

- Allow **different types**
    
- Focus on **type flexibility**
    

`let value: string | number; 

value = "hello"; // ✅ 

value = 10;      // ✅ 

value = true;    // ❌`

---

### Literal Types

- Allow **exact values only**
    
- Focus on **value restriction**
    

`let role: "admin" | "user"; 

role = "admin";   // ✅ 

role = "manager"; // ❌`

## Side-by-side comparison

|Feature|Union Type|Literal Type|
|---|---|---|
|What it combines|Types|Exact values|
|Example|`string \| number`|`"admin"`|
|Restriction level|Low|Very strict|
|Real use|APIs, inputs|Status, roles|

## Final interview-ready answer

> **Union types allow a variable to hold multiple possible types, such as string or number. Literal types restrict a variable to specific exact values. When we want strict control over allowed values without runtime errors, we use literal types, often combined using unions.**

