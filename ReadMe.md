# Using ES2015 in Node.js

This document outlines modern JavaScript features that I encourage you to use in Node.js per Node.js major version. A
language feature is encouraged when it provides a notable advantage in one or more of these categories:

- Code readability
- Performance
- Runtime safety

And features are actively discouraged as long as a notable performance impact is considered to be too high compared to
the alternative.

## Node.js 5

### `const` and `let` variable declarations

Advantages over `var`:
- Block scoped instead of function scoped, makes it behave much more as the syntax would indicate.
- `const` protects developers from accidental re-assignment to a variable.

Disadvantages:
- At this point, `let` is slightly slower than `var`, but not enough to discourage its use.

More documentation:
[const on MDN](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Statements/const) |
[let on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)

### Class syntax

Class syntax makes it much easier and concise to implement classes the way many people already do.

Advantages over constructor function with prototype assignment:
- You no longer need an `inherits` helper function when doing inheritance.
- More closely matches other programming languages, making it easier for non-JS speakers to get onboard.

More documentation:
[class on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

### for-of loops

This works on all iterables (including arrays)

Example:

```js
const letters = ['a', 'b', 'c'];
for (const char of letters) {
  console.log(char);
}
```

Advantages over `for (i = 0; i < arr.length; i++)`:
- No need for a meaningless iterator variable.
- No need for `const char = letters[i];` since the element is directly useable.

Note:
> You cannot yet iterate over a plain object this way. In the future this may become possible:
> for (let [key, value] of Object.entries(obj))

More documentation:
[for-of on MDN](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Statements/for...of)

### Short object notation

When you have variables that are named the same as properties of an object you want to create, you can replace:

```js
const a = 5;
const b = 3;
const obj = { a: a, b: b };
```

With:

```js
const a = 5;
const b = 3;
const obj = { a, b };
```

Advantages:
- Chance of typos reduced
- When dealing with large objects, this can reduce the amount of noise

More documentation:
[object notation on MDN](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Operators/Object_initializer#New_notations_in_ECMAScript_2015)

### Fat arrow function notation

TODO

## Node.js 6

### Destructuring

TODO

### Rest arguments

TODO
