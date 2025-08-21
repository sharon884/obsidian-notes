
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