
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

