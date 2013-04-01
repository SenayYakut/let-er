# BlockScoper.js

Everyone knows that JavaScript (ES5 and below) only has function-level scope, meaning that `(function(foo){ .. })()` is the smallest amount of boilerplate code required to create a new scope for a `foo` variable.

It's also probably not a huge surprise to many that ES6 is going to give us the `let` operator, which will let us do things like `let (foo) { .. }` to get block-scoping for `foo`. But, who wants to wait for `let`? ES6 is still like years away from cross-browser usage.

The solution? This code-transpiler provides you the ability to do block-scoping in JavaScript **right now**.

## What does it look like?

With my patent-pending technology, you can now write block-scope declarations in JavaScript with `let`-statement code:

```js
let (foo) {
  foo = "foo";
  console.log("foo");
}

foo; // Reference Error!
```

## How does it work?

"BlockScoper.js" code transpiler will take any JS you have which uses let statements like the above, and transform it to this ES3-compatible code for block-scoping:

```js
try{""()}catch
(foo) {
  foo = "foo";
  console.log("foo");
}

foo; // Reference Error!
```

## Boom!

Yep. That's it. Impressed? I thought so.

Oh yeah, this is all MIT licensed. Enjoy.