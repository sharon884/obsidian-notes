
# Numbers

In modern JavaScript, there are two types of numbers:

1. Regular numbers in JavaScript are stored in 64-bit format [IEEE-754](https://en.wikipedia.org/wiki/IEEE_754), also known as “double precision floating point numbers”. These are numbers that we’re using most of the time

2. BigInt numbers represent integers of arbitrary length. They are sometimes needed because a regular integer number can’t safely exceed `(253-1)` or be less than `-(253-1)`, as we mentioned earlier in the chapter [Data types](https://javascript.info/types). As bigints are used in a few special areas, we devote them to a special chapter [BigInt](https://javascript.info/bigint).


## [More ways to write a number](https://javascript.info/number#more-ways-to-write-a-number)

Imagine we need to write 1 billion. The obvious way is:

```javascript
let billion = 1000000000;
```

We also can use underscore `_` as the separator:

```javascript
let billion = 1_000_000_000;
```

Here the underscore `_` plays the role of the “[syntactic sugar](https://en.wikipedia.org/wiki/Syntactic_sugar)”, it makes the number more readable. The JavaScript engine simply ignores `_` between digits, so it’s exactly the same one billion as above.



## [Rounding](https://javascript.info/number#rounding)

One of the most used operations when working with numbers is rounding.

There are several built-in functions for rounding:

`Math.floor`

Rounds down: `3.1` becomes `3`, and `-1.1` becomes `-2`.

`Math.ceil`

Rounds up: `3.1` becomes `4`, and `-1.1` becomes `-1`.

`Math.round`

Rounds to the nearest integer: `3.1` becomes `3`, `3.6` becomes `4`. In the middle cases `3.5` rounds up to `4`, and `-3.5` rounds up to `-3`.

`Math.trunc` (not supported by Internet Explorer)

Removes anything after the decimal point without rounding: `3.1` becomes `3`, `-1.1` becomes `-1`.

Here’s the table to summarize the differences between them:


## 1️⃣ **`isNaN()`**

**Purpose:**

- Checks whether a value is **“Not a Number” (NaN)**.
    
- Returns **true** if the value is NaN, otherwise **false**.
    

### Syntax:

`isNaN(value)`

### Examples:

`isNaN(123);        // false → 123 is a number
isNaN("123");      // false → "123" can be converted to number
isNaN("hello");    // true → "hello" cannot be converted to number isNaN(NaN);        // true → NaN itself`

**Key Note:**

- `isNaN` first tries to **convert the value to a number** before checking.
    
- To strictly check if something is NaN, use `Number.isNaN(value)` (does not coerce).
    

`Number.isNaN("hello"); // false Number.isNaN(NaN);     // true`

---

## 2️⃣ **`isFinite()`**

**Purpose:**

- Checks whether a value is a **finite number** (not `Infinity`, `-Infinity`, or `NaN`).
    
- Returns **true** if finite, otherwise **false**.
    

### Syntax:

`isFinite(value)`

### Examples:

`isFinite(123);       // true → finite 
isFinite("123");     // true → string converted to number
isFinite(Infinity);  // false → not finite 
isFinite(-Infinity); // false → not finite 
isFinite(NaN);       // false → NaN is not finite
isFinite("hello");   // false → cannot convert to number`

**Key Note:**

- Like `isNaN`, `isFinite` **coerces strings** to numbers first.
    
- To strictly check a number, use `Number.isFinite(value)` (does not coerce).
    

`Number.isFinite("123"); // false Number.isFinite(123);   // true`

---

### 3️⃣ **Quick Comparison**

|Function|Checks|Coerces to number?|Example|
|---|---|---|---|
|`isNaN(value)`|Whether **not a number**|✅ Yes|isNaN("hello") → true|
|`Number.isNaN()`|Strictly **NaN only**|❌ No|Number.isNaN("hello") → false|
|`isFinite(value)`|Whether **finite number**|✅ Yes|isFinite("123") → true|
|`Number.isFinite()`|Strictly finite number|❌ No|Number.isFinite("123") → false|

---

💡 **Summary:**

- `isNaN` → checks “not a number”
    
- `isFinite` → checks “finite number”
    
- Use `Number.isNaN` / `Number.isFinite` for **strict checks** without type coercion


## 1️⃣ **`parseInt()`**

**Purpose:**

- Converts a **string** into an **integer** (whole number).
    
- Ignores any non-numeric characters after the number.
    

### Syntax:

`parseInt(string, radix)`

- `string` → the value to convert
    
- `radix` → optional, base of number system (default is 10)
    

### Examples:

`parseInt("123");        // 123 
parseInt("123.45");     // 123 → only integer part
parseInt("10abc");      // 10 → stops parsing at non-number
parseInt("abc10");      // NaN → starts with non-number 
parseInt("11", 2);      // 3 → binary string converted to decimal`

**Key Notes:**

- Returns **NaN** if the string does not start with a number.
    
- Ignores decimal part (truncates to integer).
    

---

## 2️⃣ **`parseFloat()`**

**Purpose:**

- Converts a **string** into a **floating-point number** (decimal allowed).
    

### Syntax:

`parseFloat(string)`

### Examples:

`parseFloat("123");        // 123 
parseFloat("123.45");     // 123.45 → keeps decimal
parseFloat("10.5abc");    // 10.5 → stops at first invalid character parseFloat("abc10.5");    // NaN → starts with non-number`

**Key Notes:**

- Returns **NaN** if the string does not start with a number.
    
- Preserves decimal part.
    

---

## 3️⃣ **Quick Comparison**

|Function|Converts to|Keeps decimal?|Example|
|---|---|---|---|
|`parseInt()`|Integer|❌ No|"123.45" → 123|
|`parseFloat()`|Floating number|✅ Yes|"123.45" → 123.45|

---

### 4️⃣ **Tip**

- Both functions **ignore trailing non-numeric characters**.
    
- Both return **NaN** if the string does not start with a numeric character.
    

---

💡 **Example Combined:**

`let a = "150px"; console.log(parseInt(a));   // 150 console.log(parseFloat(a)); // 150  let b = "12.75kg"; console.log(parseInt(b));   // 12 console.log(parseFloat(b)); // 12.75`