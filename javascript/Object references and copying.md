One of the fundamental differences of objects versus primitives is that objects are stored and copied “by reference”, whereas primitive values: strings, numbers, booleans, etc – are always copied “as a whole value”.

Here we put a copy of `message` into `phrase`:

```javascript
let message = "Hello!";
let phrase = message;
```

As a result we have two independent variables, each one storing the string `"Hello!"`.

**A variable assigned to an object stores not the object itself, but its “address in memory” – in other words “a reference” to it.**

Let’s look at an example of such a variable:

```javascript
let user = {
  name: "John"
};
```

![[Pasted image 20250821120535.png]]


When we perform actions with the object, e.g. take a property `user.name`, the JavaScript engine looks at what’s at that address and performs the operation on the actual object.


**When an object variable is copied, the reference is copied, but the object itself is not duplicated.**

For instance:

```javascript
let user = { name: "John" };

let admin = user; // copy the reference
```

Now we have two variables, each storing a reference to the same object:

![[Pasted image 20250821120704.png]]


As you can see, there’s still one object, but now with two variables that reference it.

We can use either variable to access the object and modify its contents:

[](https://javascript.info/object-copy# "run")

[](https://javascript.info/object-copy# "open in sandbox")

```javascript
let user = { name: 'John' };

let admin = user;

admin.name = 'Pete'; // changed by the "admin" reference

alert(user.name); // 'Pete', changes are seen from the "user" reference
```


## [Comparison by reference](https://javascript.info/object-copy#comparison-by-reference)

Two objects are equal only if they are the same object.

For instance, here `a` and `b` reference the same object, thus they are equal:

[](https://javascript.info/object-copy# "run")

[](https://javascript.info/object-copy# "open in sandbox")

```javascript
let a = {};
let b = a; // copy the reference

alert( a == b ); // true, both variables reference the same object
alert( a === b ); // true
```

And here two independent objects are not equal, even though they look alike (both are empty):

[](https://javascript.info/object-copy# "run")

[](https://javascript.info/object-copy# "open in sandbox")

```javascript
let a = {};
let b = {}; // two independent objects

alert( a == b ); // false
```

Const objects can be modified

An important side effect of storing objects as references is that an object declared as `const` _can_ be modified.

For instance:

[](https://javascript.info/object-copy# "run")

[](https://javascript.info/object-copy# "open in sandbox")

```javascript
const user = {
  name: "John"
};

user.name = "Pete"; // (*)

alert(user.name); // Pete
```

It might seem that the line `(*)` would cause an error, but it does not. The value of `user` is constant, it must always reference the same object, but properties of that object are free to change.

In other words, the `const user` gives an error only if we try to set `user=...` as a whole.

That said, if we really need to make constant object properties, it’s also possible, but using totally different methods.



Ah! `Object.assign` is a **built-in JavaScript method** used to **copy properties from one or more source objects to a target object**. Let me explain in simple terms.

---

## **Syntax**

`Object.assign(target, ...sources)`

- **target** → the object you want to copy properties **into**.
    
- **sources** → one or more objects whose properties you want to **copy**.
    
- Returns the **target object** after copying.
    

---

## **Examples**

### 1️⃣ Simple copy

`let user = { name: "sharon", age: 20 };
let admin = Object.assign({}, user);
console.log(admin); // { name: "sharon", age: 20 }  admin.name = "sherluck";
console.log(user.name); // "sharon" ✅ original object unchanged`

- Here `{}` is the **target object** → we create a **new object** and copy `user`’s properties into it.
    
- This is often used to make a **shallow copy**.
    

---

### 2️⃣ Merge multiple objects

`let user = { name: "sharon" };
let details = { age: 20, city: "Delhi" }; 
let merged = Object.assign({}, user, details); console.log(merged); // { name: "sharon", age: 20, city: "Delhi" }`

- Properties from all sources are copied into the target object.
    
- If properties have the **same key**, the **last source overrides** the previous ones.
    

`let a = { name: "sharon" };
let b = { name: "sherluck", age: 20 }; 
let result = Object.assign({}, a, b);
console.log(result); // { name: "sherluck", age: 20 } ✅ b.name overrides a.name`

---

### 3️⃣ Important notes

- `Object.assign` **creates a shallow copy**, not deep copy.
    
    - Nested objects are still **shared by reference**.
        

`let user = { name: "sharon", address: { city: "Delhi" } };
let admin = Object.assign({}, user); 
admin.address.city = "Mumbai"; console.log(user.address.city); // "Mumbai" ❌ nested object is shared`

- For **deep copies**, you need other methods like `structuredClone()` or JSON methods.
    

---

So in short:

> `Object.assign` = **copy/merge properties from source(s) to target**.  
> Great for shallow copies or merging objects.




## [Nested cloning](https://javascript.info/object-copy#nested-cloning)

Until now we assumed that all properties of `user` are primitive. But properties can be references to other objects.

Like this:

[](https://javascript.info/object-copy# "run")

[](https://javascript.info/object-copy# "open in sandbox")

```javascript
let user = {
  name: "John",
  sizes: {
    height: 182,
    width: 50
  }
};

alert( user.sizes.height ); // 182
```

Now it’s not enough to copy `clone.sizes = user.sizes`, because `user.sizes` is an object, and will be copied by reference, so `clone` and `user` will share the same sizes:

[](https://javascript.info/object-copy# "run")

[](https://javascript.info/object-copy# "open in sandbox")

```javascript
let user = {
  name: "John",
  sizes: {
    height: 182,
    width: 50
  }
};

let clone = Object.assign({}, user);

alert( user.sizes === clone.sizes ); // true, same object

// user and clone share sizes
user.sizes.width = 60;    // change a property from one place
alert(clone.sizes.width); // 60, get the result from the other one
```

To fix that and make `user` and `clone` truly separate objects, we should use a cloning loop that examines each value of `user[key]` and, if it’s an object, then replicate its structure as well. That is called a “deep cloning” or “structured cloning”. There’s [structuredClone](https://developer.mozilla.org/en-US/docs/Web/API/structuredClone) method that implements deep cloning.



### [structuredClone](https://javascript.info/object-copy#structuredclone)

The call `structuredClone(object)` clones the `object` with all nested properties.

Here’s how we can use it in our example:

[](https://javascript.info/object-copy# "run")

[](https://javascript.info/object-copy# "open in sandbox")

```javascript
let user = {
  name: "John",
  sizes: {
    height: 182,
    width: 50
  }
};

let clone = structuredClone(user);

alert( user.sizes === clone.sizes ); // false, different objects

// user and clone are totally unrelated now
user.sizes.width = 60;    // change a property from one place
alert(clone.sizes.width); // 50, not related
```

The `structuredClone` method can clone most data types, such as objects, arrays, primitive values.

It also supports circular references, when an object property references the object itself (directly or via a chain or references).

For instance:

[](https://javascript.info/object-copy# "run")

[](https://javascript.info/object-copy# "open in sandbox")

```javascript
let user = {};
// let's create a circular reference:
// user.me references the user itself
user.me = user;

let clone = structuredClone(user);
alert(clone.me === clone); // true
```

As you can see, `clone.me` references the `clone`, not the `user`! So the circular reference was cloned correctly as well.

Although, there are cases when `structuredClone` fails.

For instance, when an object has a function property:

[](https://javascript.info/object-copy# "run")

[](https://javascript.info/object-copy# "open in sandbox")

```javascript
// error
structuredClone({
  f: function() {}
});
```

Function properties aren’t supported.

To handle such complex cases we may need to use a combination of cloning methods, write custom code or, to not reinvent the wheel, take an existing implementation, for instance [_.cloneDeep(obj)](https://lodash.com/docs#cloneDeep) from the JavaScript library [lodash](https://lodash.com/).

## [Summary](https://javascript.info/object-copy#summary)

Objects are assigned and copied by reference. In other words, a variable stores not the “object value”, but a “reference” (address in memory) for the value. So copying such a variable or passing it as a function argument copies that reference, not the object itself.

All operations via copied references (like adding/removing properties) are performed on the same single object.

To make a “real copy” (a clone) we can use `Object.assign` for the so-called “shallow copy” (nested objects are copied by reference) or a “deep cloning” function `structuredClone` or use a custom cloning implementation, such as [_.cloneDeep(obj)](https://lodash.com/docs#cloneDeep).

[](https://javascript.info/object)[](https://javascript.info/garbage-collection)


