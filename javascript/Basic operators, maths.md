

# 🚀 JavaScript Operators Cheat Sheet

## 🔹 Arithmetic

|Operator|Meaning|Example|Result|
|---|---|---|---|
|`+`|Addition|`5 + 2`|`7`|
|`-`|Subtraction|`5 - 2`|`3`|
|`*`|Multiplication|`5 * 2`|`10`|
|`/`|Division|`5 / 2`|`2.5`|
|`%`|Modulus (remainder)|`5 % 2`|`1`|
|`**`|Exponentiation|`5 ** 2`|`25`|
|`++`|Increment|`x=5; ++x`|`6`|
|`--`|Decrement|`x=5; x--`|`4`|

---

## 🔹 Assignment

| Operator | Meaning           | Example          | Result |
| -------- | ----------------- | ---------------- | ------ |
| `=`      | Assign            | `x = 5`          | `5`    |
| `+=`     | Add & assign      | `x = 5; x += 2`  | `7`    |
| `-=`     | Subtract & assign | `x = 5; x -= 2`  | `3`    |
| `*=`     | Multiply & assign | `x = 5; x *= 2`  | `10`   |
| `/=`     | Divide & assign   | `x = 10; x /= 2` | `5`    |
| `%=`     | Modulus & assign  | `x = 5; x %= 2`  | `1`    |
| `**=`    | Power & assign    | `x = 3; x **= 2` | `9`    |

---

## 🔹 Comparison

|Operator|Meaning|Example|Result|
|---|---|---|---|
|`==`|Equal (loose)|`5 == "5"`|`true`|
|`===`|Equal (strict)|`5 === "5"`|`false`|
|`!=`|Not equal (loose)|`5 != "5"`|`false`|
|`!==`|Not equal (strict)|`5 !== "5"`|`true`|
|`>`|Greater than|`5 > 2`|`true`|
|`<`|Less than|`5 < 2`|`false`|
|`>=`|Greater or equal|`5 >= 5`|`true`|
|`<=`|Less or equal|`5 <= 2`|`false`|

---

## 🔹 Logical

| Operator | Meaning | Example            | Result  |
| -------- | ------- | ------------------ | ------- |
| `&&`     | AND     | `(5 > 2 && 3 > 1)` | `true`  |
| `        |         | `                  | OR      |
| `!`      | NOT     | `!(5 > 2)`         | `false` |

---

## 🔹 Bitwise

|Operator|Meaning|
|---|---|
|`&`|AND|
|`|`|
|`^`|XOR|
|`~`|NOT|
|`<<`|Left shift|
|`>>`|Right shift|
|`>>>`|Unsigned right shift|

---

## 🔹 Ternary

`let age = 18; let result = (age >= 18) ? "Adult" : "Minor";`

---

## 🔹 Type

|Operator|Meaning|Example|
|---|---|---|
|`typeof`|Type of variable|`typeof "hello"` → `"string"`|
|`instanceof`|Checks object type|`[] instanceof Array` → `true`|

---

## 🔹 Spread & Rest

`// Spread let arr = [1, 2, 3];
let copy = [...arr]; // [1,2,3]  


// Rest function sum(...nums) {

return nums.reduce((a,b) => a+b, 0);

} console.log(sum(1,2,3)); // 6`



## [Terms: “unary”, “binary”, “operand”](https://javascript.info/operators#terms-unary-binary-operand)


## [Maths](https://javascript.info/operators#maths)

The following math operations are supported:

- Addition `+`,
- Subtraction `-`,
- Multiplication `*`,
- Division `/`,
- Remainder `%`,
- Exponentiation `**`.

## [String concatenation with binary +](https://javascript.info/operators#string-concatenation-with-binary)

Let’s meet the features of JavaScript operators that are beyond school arithmetics.

Usually, the plus operator `+` sums numbers.

But, if the binary `+` is applied to strings, it merges (concatenates) them:

```javascript
let s = "my" + "string";
alert(s); // mystring
```

Note that if any of the operands is a string, then the other one is converted to a string too.

For example:

[](https://javascript.info/operators# "run")

[](https://javascript.info/operators# "open in sandbox")

```javascript
alert( '1' + 2 ); // "12"
alert( 2 + '1' ); // "21"
```

See, it doesn’t matter whether the first operand is a string or the second one.

Here’s a more complex example:

[](https://javascript.info/operators# "run")

[](https://javascript.info/operators# "open in sandbox")

```javascript
alert(2 + 2 + '1' ); // "41" and not "221"
```

Here, operators work one after another. The first `+` sums two numbers, so it returns `4`, then the next `+` adds the string `1` to it, so it’s like `4 + '1' = '41'`.

[](https://javascript.info/operators# "run")

[](https://javascript.info/operators# "open in sandbox")

```javascript
alert('1' + 2 + 2); // "122" and not "14"
```


## [Numeric conversion, unary +](https://javascript.info/operators#numeric-conversion-unary)

The plus `+` exists in two forms: the binary form that we used above and the unary form.

The unary plus or, in other words, the plus operator `+` applied to a single value, doesn’t do anything to numbers. But if the operand is not a number, the unary plus converts it into a number.

For example:

[](https://javascript.info/operators# "run")

[](https://javascript.info/operators# "open in sandbox")

```javascript
// No effect on numbers
let x = 1;
alert( +x ); // 1

let y = -2;
alert( +y ); 4

// Converts non-numbers
alert( +true ); // 1
alert( +"" );   // 0
```

## [Assignment](https://javascript.info/operators#assignment)

Let’s note that an assignment `=` is also an operator. It is listed in the precedence table with the very low priority of `2`.

That’s why, when we assign a variable, like `x = 2 * 2 + 1`, the calculations are done first and then the `=` is evaluated, storing the result in `x`.

```javascript
let x = 2 * 2 + 1;

alert( x ); // 5
```

### [Assignment = returns a value](https://javascript.info/operators#assignment-returns-a-value)


## [Increment/decrement](https://javascript.info/operators#increment-decrement)

Increasing or decreasing a number by one is among the most common numerical operations.

So, there are special operators for it:

- **Increment** `++` increases a variable by 1:
    
    [](https://javascript.info/operators# "run")
    
    [](https://javascript.info/operators# "open in sandbox")
    
    ```javascript
    let counter = 2;
    counter++;        // works the same as counter = counter + 1, but is shorter
    alert( counter ); // 3
    ```
    
- **Decrement** `--` decreases a variable by 1:
    
    [](https://javascript.info/operators# "run")
    
    [](https://javascript.info/operators# "open in sandbox")
    
    ```javascript
    let counter = 2;
    counter--;        // works the same as counter = counter - 1, but is shorter
    alert( counter ); // 1
    ```

## [Bitwise operators](https://javascript.info/operators#bitwise-operators)

Bitwise operators treat arguments as 32-bit integer numbers and work on the level of their binary representation.

These operators are not JavaScript-specific. They are supported in most programming languages.

The list of operators:

- AND ( `&` )
- OR ( `|` )
- XOR ( `^` )
- NOT ( `~` )
- LEFT SHIFT ( `<<` )
- RIGHT SHIFT ( `>>` )
- ZERO-FILL RIGHT SHIFT ( `>>>` )

## [Comma](https://javascript.info/operators#comma)

The comma operator `,` is one of the rarest and most unusual operators. Sometimes, it’s used to write shorter code, so we need to know it in order to understand what’s going on.

The comma operator allows us to evaluate several expressions, dividing them with a comma `,`. Each of them is evaluated but only the result of the last one is returned.

For example:

[](https://javascript.info/operators# "run")

[](https://javascript.info/operators# "open in sandbox")

```javascript
let a = (1 + 2, 3 + 4);

alert( a ); // 7 (the result of 3 + 4)
```

Here, the first expression `1 + 2` is evaluated and its result is thrown away. Then, `3 + 4` is evaluated and returned as the result.


