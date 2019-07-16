---
title: JavaScript Concept 12 - Modules in JavaScript (CommonJS, Babel & Webpack)
date: 2019-07-16 16:07:38
category: JavaScript
---

## Why Module is important?

- Reusability
- Composability
- Leverage
- Isolation (Easy to maintain)
- Organization

## CommonJS

CommonJs is one of the standards which **NodeJS** has been using. Before ES6, browsers didn't support module system. Basically Syntaxs like CommonJS and AMD made it possible for browsers and server engines to use module system.

This is how the module system works in CommonJS.

```js{7,11}
// greeting.js

let hello = function() {
  console.log('hello')
}

exports.greeting = hello

// example.js

let greeting = require('./greeting.js')

greeting.hello() // 'hello'
```

## Babel & Webpack

Though ES Modules now landed in the browsers, there still are old versions of browsers or servers that don't understand the syntax of ES Modules. To make our codes compatible for those environmnets, transpiling process (put simply, **translating es6 syntax to es5**) is necessary.

The well-known ones are **babel** and bundling tool, **webpack**.
A JavaScript bundler gathers the separated codes into one .js file and you can set it up for es5 conversioin as well if there are codes written in es6.

## Conclusion

Transpilers are still needed for a smooth unification of client-side code and on server-side(NodeJS) code.

<br>
<br>

_Reference_

https://flaviocopes.com/es-modules/

<br>
<br>
