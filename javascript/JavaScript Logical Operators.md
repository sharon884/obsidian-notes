
## 1. **AND (`&&`)**

- Returns **true** if both are true.
    
- Stops at the first **falsy** value.
    
- If all are truthy → returns the **last value**.
    

`true && true        // true true && false       // false "Hello" && 123      // 123 "" && "JS"          // ""`

---

## 2. **OR (`||`)**

- Returns **true** if at least one is true.
    
- Stops at the first **truthy** value.
    
- If all are falsy → returns the **last value**.
    

`true || false       // true false || false      // false "" || "Hi"          // "Hi" 0 || null || "JS"   // "JS"`

---

## 3. **NOT (`!`)**

- Inverts the value (truthy → false, falsy → true).
    

`!true       // false !false      // true !0          // true !"Hello"    // false`

---

## 4. **Nullish Coalescing (`??`)**

- Returns right-hand side **only if left-hand side is `null` or `undefined`**.
    
- Different from `||` → `||` treats `0`, `""`, `false` as falsy, but `??` does not.
    

`null ?? "Default"   // "Default" undefined ?? "Hi"   // "Hi" 0 ?? 100            // 0 "" ?? "JS"          // ""`

---

## 5. **Optional Chaining (`?.`)**

- Prevents error if a property is missing.
    
- Returns `undefined` instead of throwing an error.
    

`let user = { profile: { name: "Sharon" } };  user.profile?.name     // "Sharon" user.contact?.phone    // undefined (no error)`

---

## 🔹 Operator Precedence

Order of execution:

1. `!` (NOT)
    
2. `&&` (AND)
    
3. `||` (OR)
    
4. `??` (Nullish coalescing)



# Operator Precedence (Highest → Lowest)

1. **`!` (NOT)**
    
    - Runs first
        
    - Converts truthy/falsy → boolean opposite
        
    
    `!true // false`
    
2. **`&&` (AND)**
    
    - Runs before OR and Nullish
        
    - Stops at first falsy (or last truthy)
        
    
    `true && false // false`
    
3. **`||` (OR)**
    
    - Runs after AND
        
    - Stops at first truthy (or last falsy)
        
    
    `false || "JS" // "JS"`
    
4. **`??` (Nullish Coalescing)**
    
    - Runs last (lowest precedence)
        
    - Only checks for `null` or `undefined`
        
    
    `null ?? "Default" // "Default"`


# 🔑 JavaScript Logical Operators Cheat Sheet

### **1. AND (`&&`)**

- Returns the **first falsy** value.
    
- If none are falsy → returns the **last truthy** value.
    

👉 Examples:

`true && "Hello"   // "Hello" 0 && "Hello"      // 0 "Hi" && 123       // 123`

---

### **2. OR (`||`)**

- Returns the **first truthy** value.
    
- If none are truthy → returns the **last falsy** value.
    

👉 Examples:

`"Hi" || "Hello"   // "Hi" "" || "Hello"     // "Hello" 0 || null || 42   // 42`

---

### **3. Nullish Coalescing (`??`)**

- Returns the **right-hand value only if left is `null` or `undefined`**.
    
- Otherwise → returns the left value.
    

👉 Examples:

`null ?? "Default"      // "Default" undefined ?? "Yes"     // "Yes" 0 ?? "Default"         // 0 "" ?? "Default"        // ""`