
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

