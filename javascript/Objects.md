
As we know from the chapter [Data types](https://javascript.info/types), there are eight data types in JavaScript. Seven of them are called “primitive”, because their values contain only a single thing (be it a string or a number or whatever).


An object can be created with figure brackets `{…}` with an optional list of _properties_. A property is a “key: value” pair, where `key` is a string (also called a “property name”), and `value` can be anything.


![[Pasted image 20250821100619.png]]

Usually, the figure brackets `{...}` are used. That declaration is called an _object literal_.


## [Literals and properties](https://javascript.info/object#literals-and-properties)

We can immediately put some properties into `{...}` as “key: value” pairs:

```javascript
let user = {     // an object
  name: "John",  // by key "name" store value "John"
  age: 30        // by key "age" store value 30
};
```

A property has a key (also known as “name” or “identifier”) before the colon `":"` and a value to the right of it.

In the `user` object, there are two properties:

1. The first property has the name `"name"` and the value `"John"`.
2. The second one has the name `"age"` and the value `30`.

The resulting `user` object can be imagined as a cabinet with two signed files labeled “name” and “age”.

We can add, remove and read files from it at any time.

Property values are accessible using the dot notation:

```javascript
// get property values of the object:
alert( user.name ); // John
alert( user.age ); // 30
```

The value can be of any type. Let’s add a boolean one:

```javascript
user.isAdmin = true;
```

To remove a property, we can use the `delete` operator:

```javascript
delete user.age;
```

We can also use multiword property names, but then they must be quoted:

```javascript
let user = {
  name: "John",
  age: 30,
  "likes birds": true  // multiword property name must be quoted
};
```

The last property in the list may end with a comma:

```javascript
let user = {
  name: "John",
  age: 30,
}
```

That is called a “trailing” or “hanging” comma. Makes it easier to add/remove/move around properties, because all lines become alike.


## [Square brackets](https://javascript.info/object#square-brackets)

For multiword properties, the dot access doesn’t work:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
// this would give a syntax error
user.likes birds = true
```

JavaScript doesn’t understand that. It thinks that we address `user.likes`, and then gives a syntax error when comes across unexpected `birds`.

The dot requires the key to be a valid variable identifier. That implies: contains no spaces, doesn’t start with a digit and doesn’t include special characters (`$` and `_` are allowed).

There’s an alternative “square bracket notation” that works with any string:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
let user = {};

// set
user["likes birds"] = true;

// get
alert(user["likes birds"]); // true

// delete
delete user["likes birds"];
```

Now everything is fine. Please note that the string inside the brackets is properly quoted (any type of quotes will do).

Square brackets also provide a way to obtain the property name as the result of any expression – as opposed to a literal string – like from a variable as follows:

```javascript
let key = "likes birds";

// same as user["likes birds"] = true;
user[key] = true;
```

Here, the variable `key` may be calculated at run-time or depend on the user input. And then we use it to access the property. That gives us a great deal of flexibility.

For instance:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
let user = {
  name: "John",
  age: 30
};

let key = prompt("What do you want to know about the user?", "name");

// access by variable
alert( user[key] ); // John (if enter "name")
```

The dot notation cannot be used in a similar way:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
let user = {
  name: "John",
  age: 30
};

let key = "name";
alert( user.key ) // undefined
```

### [Computed properties](https://javascript.info/object#computed-properties)

We can use square brackets in an object literal, when creating an object. That’s called _computed properties_.

For instance:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
let fruit = prompt("Which fruit to buy?", "apple");

let bag = {
  [fruit]: 5, // the name of the property is taken from the variable fruit
};

alert( bag.apple ); // 5 if fruit="apple"
```

The meaning of a computed property is simple: `[fruit]` means that the property name should be taken from `fruit`.

So, if a visitor enters `"apple"`, `bag` will become `{apple: 5}`.

Essentially, that works the same as:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
let fruit = prompt("Which fruit to buy?", "apple");
let bag = {};

// take property name from the fruit variable
bag[fruit] = 5;
```

…But looks nicer.

We can use more complex expressions inside square brackets:

```javascript
let fruit = 'apple';
let bag = {
  [fruit + 'Computers']: 5 // bag.appleComputers = 5
};
```

Square brackets are much more powerful than dot notation. They allow any property names and variables. But they are also more cumbersome to write.

So most of the time, when property names are known and simple, the dot is used. And if we need something more complex, then we switch to square brackets.


## [Property value shorthand](https://javascript.info/object#property-value-shorthand)

In real code, we often use existing variables as values for property names.

For instance:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
function makeUser(name, age) {
  return {
    name: name,
    age: age,
    // ...other properties
  };
}

let user = makeUser("John", 30);
alert(user.name); // John
```

In the example above, properties have the same names as variables. The use-case of making a property from a variable is so common, that there’s a special _property value shorthand_ to make it shorter.

Instead of `name:name` we can just write `name`, like this:

```javascript
function makeUser(name, age) {
  return {
    name, // same as name: name
    age,  // same as age: age
    // ...
  };
}
```

We can use both normal properties and shorthands in the same object:

```javascript
let user = {
  name,  // same as name:name
  age: 30
};
```


## [Property names limitations](https://javascript.info/object#property-names-limitations)

As we already know, a variable cannot have a name equal to one of the language-reserved words like “for”, “let”, “return” etc.

But for an object property, there’s no such restriction:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
// these properties are all right
let obj = {
  for: 1,
  let: 2,
  return: 3
};

alert( obj.for + obj.let + obj.return );  // 6
```

In short, there are no limitations on property names. They can be any strings or symbols (a special type for identifiers, to be covered later).

Other types are automatically converted to strings.

For instance, a number `0` becomes a string `"0"` when used as a property key:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
let obj = {
  0: "test" // same as "0": "test"
};

// both alerts access the same property (the number 0 is converted to string "0")
alert( obj["0"] ); // test
alert( obj[0] ); // test (same property)
```

There’s a minor gotcha with a special property named `__proto__`. We can’t set it to a non-object value:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
let obj = {};
obj.__proto__ = 5; // assign a number
alert(obj.__proto__); // [object Object] - the value is an object, didn't work as intended
```

As we see from the code, the assignment to a primitive `5` is ignored.

We’ll cover the special nature of `__proto__` in [subsequent chapters](https://javascript.info/prototype-inheritance), and suggest the [ways to fix](https://javascript.info/prototype-methods) such behavior.


## [Property existence test, “in” operator](https://javascript.info/object#property-existence-test-in-operator)

A notable feature of objects in JavaScript, compared to many other languages, is that it’s possible to access any property. There will be no error if the property doesn’t exist!

Reading a non-existing property just returns `undefined`. So we can easily test whether the property exists:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
let user = {};

alert( user.noSuchProperty === undefined ); // true means "no such property"
```

There’s also a special operator `"in"` for that.

The syntax is:

```javascript
"key" in object
```

For instance:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
let user = { name: "John", age: 30 };

alert( "age" in user ); // true, user.age exists
alert( "blabla" in user ); // false, user.blabla doesn't exist
```

Please note that on the left side of `in` there must be a _property name_. That’s usually a quoted string.

If we omit quotes, that means a variable should contain the actual name to be tested. For instance:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
let user = { age: 30 };

let key = "age";
alert( key in user ); // true, property "age" exists
```

Why does the `in` operator exist? Isn’t it enough to compare against `undefined`?

Well, most of the time the comparison with `undefined` works fine. But there’s a special case when it fails, but `"in"` works correctly.

It’s when an object property exists, but stores `undefined`:

[](https://javascript.info/object# "run")

[](https://javascript.info/object# "open in sandbox")

```javascript
let obj = {
  test: undefined
};

alert( obj.test ); // it's undefined, so - no such property?

alert( "test" in obj ); // true, the property does exist!
```

In the code above, the property `obj.test` technically exists. So the `in` operator works right.

Situations like this happen very rarely, because `undefined` should not be explicitly assigned. We mostly use `null` for “unknown” or “empty” values. So the `in` operator is an exotic guest in the code.


