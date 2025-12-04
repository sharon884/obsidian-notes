
- **Definition:** JavaScript automatically or manually converts a value from one type to another.
    
- It’s the general **concept** that covers both implicit and explicit conversion.

### **Implicit Type Coercion**

- **Definition:** JavaScript automatically converts a value **without you explicitly asking for it**.
    
- Happens **under the hood**, often in operations, comparisons, or expressions.
    

**Examples:**

`// Number + String → String let result = 5 + "5"; 
// "55" → 5 converted to "5" 

// Boolean in numeric context console.log(true + 1);  // 2 → true converted to 1 


// Loose equality console.log(0 == false); // true → false coerced to 0`

**Key:** You don’t write the conversion; JS does it automatically.


### **Explicit Type Coercion**



- **Definition:** You **manually convert** a value from one type to another using functions or operators.
    

**Examples:**

`// String to Number let num = Number("123");  // 123 

// Number to String let str = String(456);    // "456"  

// Boolean conversion let isTrue = Boolean(0);  // false`

**Key:** You are intentionally converting the type.