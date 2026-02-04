
## What is a Type Alias?

A **type alias** is just a **name given to a type**.

👉 It helps us **reuse**, **simplify**, and **organize** types.

type UserId = number;

let id: UserId = 10;
So here:

UserId is an alias

Actual type is still number


## Why do we need Type Aliases?

Without `type`:

`function getUser(id: number | string | null) {}`

With `type`:

`type Id = number | string | null;

function getUser(id: Id) {}`

✔ Cleaner  
✔ Reusable  
✔ Easier to maintain

---
## Type Alias with Objects

`type User = {  

id: number;  

name: string;  

isActive: boolean; 

};`

Usage:

`const user: User = {   id: 1,  

name: "Ace",   

isActive: true, 
 
 };
 
 
 ## Interview-ready definition

> **A type alias is a way to create a custom name for any TypeScript type, including primitives, unions, objects, and functions, to improve code readability and reusability.**
> 




> - ✔ Uses the `type` keyword
    
- ✔ Creates a **named type**
    
- ✔ Can represent `string`, `number`, `null`, `undefined`, objects, functions, unions
    
- ✔ Makes code **cleaner, reusable, maintainable**
    
- ✔ Used in functions, objects, etc.



- > **A type alias is a TypeScript feature that allows us to create a custom name for a type using the `type` keyword. It can represent primitive types, unions, objects, functions, or complex combinations. Type aliases help make code cleaner, more reusable, and easier to maintain, and they are used across variables, functions, and object definitions.**`