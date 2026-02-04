

## What is a Union Type?

A **union type** means **a variable can be ONE of multiple types**.

👉 Syntax uses the pipe symbol `|`

`let value: string | number;  

value = "Ace";

value = 100; // ✅ both valid`

❌ Not allowed:

`value = true;`



## Why do we need Union Types?

Because **real-world data is not always one type**.

Examples:

- API response → `string | null`
    
- ID → `number | string`
    
- Status → `"success" | "error" | "loading"`
    

JavaScript allows anything → **TypeScript controls it safely**.


## Type Narrowing (VERY IMPORTANT)

We must **check the type before using it**.

`function printId(id: number | string) {  

if (typeof id === "string") {     

console.log(id.toUpperCase());   } else {   

console.log(id.toFixed(2));   } 

};`

This is called **type narrowing** 🔍

---

## Union Types with Literal Values

`let status: "success" | "error" | "loading";  status = "success"; // ✅ status = "failed";  // ❌`

💡 This is used A LOT in React & APIs.

---

## Union Types with Objects

`type Success = {   data: string; };  type ErrorResponse = {   error: string; };  type ApiResponse = Success | ErrorResponse;`

Usage:

`function handleResponse(res: ApiResponse) {   if ("data" in res) {     console.log(res.data);   } else {     console.log(res.error);   } }`



## Interview-ready definition

> **Union types allow a variable, parameter, or return value to have multiple possible types, and TypeScript ensures we handle all cases safely using type narrowing.**

