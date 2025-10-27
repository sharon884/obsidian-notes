
## [String Conversion](https://javascript.info/type-conversions#string-conversion)

String conversion happens when we need the string form of a value.

For example, `alert(value)` does it to show the value.

We can also call the `String(value)` function to convert a value to a string:

[](https://javascript.info/type-conversions# "run")

[](https://javascript.info/type-conversions# "open in sandbox")

```javascript
let value = true;
alert(typeof value); // boolean

value = String(value); // now value is a string "true"
alert(typeof value); // string
```


## [Numeric Conversion](https://javascript.info/type-conversions#numeric-conversion)

Numeric conversion in mathematical functions and expressions happens automatically.

For example, when division `/` is applied to non-numbers:

[](https://javascript.info/type-conversions# "run")

[](https://javascript.info/type-conversions# "open in sandbox")

```javascript
alert( "6" / "2" ); // 3, strings are converted to numbers
```

We can use the `Number(value)` function to explicitly convert a `value` to a number:

[](https://javascript.info/type-conversions# "run")

[](https://javascript.info/type-conversions# "open in sandbox")

```javascript
let str = "123";
alert(typeof str); // string

let num = Number(str); // becomes a number 123

alert(typeof num); // number
```
Explicit conversion is usually required when we read a value from a string-based source like a text form but expect a number to be entered.

If the string is not a valid number, the result of such a conversion is `NaN`. For instance:

[](https://javascript.info/type-conversions# "run")

[](https://javascript.info/type-conversions# "open in sandbox")

```javascript
let age = Number("an arbitrary string instead of a number");

alert(age); // NaN, conversion failed
```

Numeric conversion rules:

|Value|Becomes…|
|---|---|
|`undefined`|`NaN`|
|`null`|`0`|
|`true and false`|`1` and `0`|
|`string`|Whitespaces (includes spaces, tabs `\t`, newlines `\n` etc.) from the start and end are removed. If the remaining string is empty, the result is `0`. Otherwise, the number is “read” from the string. An error gives `NaN`.|

Examples:

[](https://javascript.info/type-conversions# "run")

[](https://javascript.info/type-conversions# "open in sandbox")

```javascript
alert( Number("   123   ") ); // 123
alert( Number("123z") );      // NaN (error reading a number at "z")
alert( Number(true) );        // 1
alert( Number(false) );       // 0
```

Please note that `null` and `undefined` behave differently here: `null` becomes zero while `undefined` becomes `NaN`.

Most mathematical operators also perform such conversion, we’ll see that in the next chapter.

## [Boolean Conversion](https://javascript.info/type-conversions#boolean-conversion)

Boolean conversion is the simplest one.

It happens in logical operations (later we’ll meet condition tests and other similar things) but can also be performed explicitly with a call to `Boolean(value)`.

The conversion rule:

- Values that are intuitively “empty”, like `0`, an empty string, `null`, `undefined`, and `NaN`, become `false`.
- Other values become `true`.

For instance:

[](https://javascript.info/type-conversions# "run")

[](https://javascript.info/type-conversions# "open in sandbox")

```javascript
alert( Boolean(1) ); // true
alert( Boolean(0) ); // false

alert( Boolean("hello") ); // true
alert( Boolean("") ); // false
```

Please note: the string with zero `"0"` is `true`

Some languages (namely PHP) treat `"0"` as `false`. But in JavaScript, a non-empty string is always `true`.

[](https://javascript.info/type-conversions# "run")

[](https://javascript.info/type-conversions# "open in sandbox")

```javascript
alert( Boolean("0") ); // true
alert( Boolean(" ") ); // spaces, also true (any non-empty string is true)
```

## [Summary](https://javascript.info/type-conversions#summary)

The three most widely used type conversions are to string, to number, and to boolean.

**`String Conversion`** – Occurs when we output something. Can be performed with `String(value)`. The conversion to string is usually obvious for primitive values.

**`Numeric Conversion`** – Occurs in math operations. Can be performed with `Number(value)`.

The conversion follows the rules:

|Value|Becomes…|
|---|---|
|`undefined`|`NaN`|
|`null`|`0`|
|`true / false`|`1 / 0`|
|`string`|The string is read “as is”, whitespaces (includes spaces, tabs `\t`, newlines `\n` etc.) from both sides are ignored. An empty string becomes `0`. An error gives `NaN`.|

**`Boolean Conversion`** – Occurs in logical operations. Can be performed with `Boolean(value`