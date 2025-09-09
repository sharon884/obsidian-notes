
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
