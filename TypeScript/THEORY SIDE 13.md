

## TypeScript Interface (modern reality)

In TypeScript, `interface` is mainly used to:

- Describe **object shapes**
    
- Define **contracts for data**
    
- Enforce structure in **functions, classes, APIs**



interface User {
  id: number;
  name: string;
}


const user: User = {
  id: 1,
  name: "Ace",
};

> **TypeScript interfaces are primarily used for structural typing, while traditional OOP interfaces are used for enforcing class contracts.**


### Use `interface` when:

- Defining **object shapes**
    
- Working with **classes**
    
- You want **extensibility**
    

`interface User {   name: string; } 

interface User {   age: number; }





is the type is key word used for creating literal types , union or not?`
## Direct answer

👉 **YES**, the `type` keyword **is used to create**:

- **Literal types**
    
- **Union types**
    
- **Intersection types**
    
- **Object types**
    
- **Function types**
    

But ⚠️ **`type` itself is NOT a literal or union**  
It’s just a **tool to name a type**.


