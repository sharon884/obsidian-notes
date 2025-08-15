
There are eight basic data types in JavaScript.

## [Number](https://javascript.info/types#number)

In JavaScript, `Number` is a data type. `Infinity`, `-Infinity`, and `NaN` are special values of the Number type. JavaScript does not have separate `int` or `float` types — all are just `Number`.


## [BigInt](https://javascript.info/types#bigint-type)

```javascript
// the "n" at the end means it's a BigInt
const bigInt = 1234567890123456789012345678901234567890n;
```

As `BigInt` numbers are rarely needed


## [String](https://javascript.info/types#string)

A string in JavaScript must be surrounded by quotes.

```javascript
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
```

In JavaScript, there are 3 types of quotes.

1. Double quotes: `"Hello"`.
2. Single quotes: `'Hello'`.
3. Backticks: `` `Hello` ``.

Double and single quotes are “simple” quotes. There’s practically no difference between them in JavaScript.

Backticks are “extended functionality” quotes. They allow us to embed variables and expressions into a string by wrapping them in `${…}`, for example:

[](https://javascript.info/types# "run")

[](https://javascript.info/types# "open in sandbox")

```javascript
let name = "John";

// embed a variable
alert( `Hello, ${name}!` ); // Hello, John!
```

Please note that this can only be done in backticks. Other quotes don’t have this embedding functionality!

```javascript
alert( "the result is ${1 + 2}" ); // the result is ${1 + 2} (double qu
```


## [Boolean (logical type)](https://javascript.info/types#boolean-logical-type)

The boolean type has only two values: `true` and `false`.

This type is commonly used to store yes/no values: `true` means “yes, correct”, and `false` means “no, incorrect”.

For instance:

```javascript
let nameFieldChecked = true; // yes, name field is checked
let ageFieldChecked = false; /
```

## [The “null” value](https://javascript.info/types#the-null-value)

The special `null` value does not belong to any of the types described above.

It forms a separate type of its own which contains only the `null` value:

```javascript
let age = null;
```

In JavaScript, `null` is not a “reference to a non-existing object” or a “null pointer” like in some other languages.

It’s just a special value which represents “nothing”, “empty” or “value unknown”.

The code above states that `age` is unknown.


## [The “undefined” value](https://javascript.info/types#the-undefined-value)

The special value `undefined` also stands apart. It makes a type of its own, just like `null`.

The meaning of `undefined` is “value is not assigned”.

If a variable is declared, but not assigned, then its value is `undefined`:

[](https://javascript.info/types# "run")

[](https://javascript.info/types# "open in sandbox")

```javascript
let age;

alert(age); // shows "undefined"
```

## [Objects and Symbols](https://javascript.info/types#objects-and-symbols)

The `object` type is special.

All other types are called “primitive” because their values can contain only a single thing (be it a string or a number or whatever). In contrast, objects are used to store collections of data and more complex entities


## [The typeof operator](https://javascript.info/types#type-typeof)

The `typeof` operator returns the type of the operand. It’s useful when we want to process values of different types differently or just want to do a quick check.

A call to `typeof x` returns a string with the type name:

```javascript
typeof undefined // "undefined"

typeof 0 // "number"

typeof 10n // "bigint"

typeof true // "boolean"

typeof "foo" // "string"

typeof Symbol("id") // "symbol"

typeof Math // "object"  (1)

typeof null // "object"  (2)

typeof alert // "function"  (3)
```

1. `Math` is a built-in object that provides mathematical operations. We will learn it in the chapter [Numbers](https://javascript.info/number). Here, it serves just as an example of an object.
2. The result of `typeof null` is `"object"`. That’s an officially recognized error in `typeof`, coming from very early days of JavaScript and kept for compatibility. Definitely, `null` is not an object. It is a special value with a separate type of its own. The behavior of `typeof` is wrong here.
3. The result of `typeof alert` is `"function"`, because `alert` is a function. We’ll study functions in the next chapters where we’ll also see that there’s no special “function” type in JavaScript. Functions belong to the object type. But `typeof` treats them differently, returning `"function"`. That also comes from the early days of JavaScript. Technically, such behavior isn’t correct, but can be convenient in practice.