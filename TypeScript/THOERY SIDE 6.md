

<h1>Structural Typing</h1>
Structural typing means TypeScript checks whether an object has the required properties.  
If the required properties are missing, TypeScript throws a compile-time error.



## Why this is Structural Typing (not something else)

TypeScript **does NOT care about**:

- Object name
    
- Interface name
    
- Class name
    

It **ONLY cares about structure (shape)**:

- Required properties
    
- Required method signatures
    
- Their types




<h2> Correct Example</h2>

interface User {
  name: string;
  age: number;
}

const u1 = {
  name: "Champ",
  age: 25
};

const u2 = {
  name: "Champ"
};

let user: User;

user = u1; // ✅ OK (structure matches)

user = u2; // ❌ Error (age missing

❌ Error happens because:
👉 Required property is missing
👉 Structure does not match



## What Structural Typing is NOT 

It is **not**:

- Class-based typing
    
- Name-based typing (nominal typing)
    
- Runtime checking
    

---