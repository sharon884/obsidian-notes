
## `null` vs `undefined` 

### `undefined`

> **A variable exists but has not been assigned a value.**

`let x; console.log(x); // undefined`

- Default value
    
- Set automatically by JS
    
- Means _“not assigned yet”_
    

---

### `null`

> **A value that is intentionally set to nothing.**

`let y = null;`

- Explicitly assigned
    
- Means _“no value on purpose”_
    

---

## Key Difference 

| Point       | `undefined`   | `null`                   |
| ----------- | ------------- | ------------------------ |
| Who sets it | JavaScript    | Developer                |
| Meaning     | Missing value | Intentional empty        |
| Default     | ✅ Yes         | ❌ No                     |
| Type        | `undefined`   | `null` (object in JS 😅) |

---

## TypeScript Strict Mode

`let name: string;  name = null;       // ❌ Error name = undefined;  // ❌ Error`

You must **explicitly allow them**:

`let name: string | null | undefined;`

---

## Interview Trap

**Q:** Are `null` and `undefined` the same?

❌ Wrong:

`null == undefined // true`

✅ Correct:

`null === undefined // false`

---

## Real-World Example 

- `undefined` → Form field not touched
    
- `null` → User cleared the field
    

---

## One-Line Interview Answer 

> **`undefined` means a value has not been assigned, while `null` is an explicitly assigned empty value. TypeScript treats them as separate types under strict null checks.**

---

## Ultra-Short Version

> **`undefined` = missing  
> `null` = intentionally empty**

---