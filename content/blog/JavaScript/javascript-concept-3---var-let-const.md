---
title: JavaScript Concept 3 - var let const
date: 2019-07-03 19:07:21
category: JavaScript
---

## What's the difference between var, let, and const?

**let & const**

- Not hoisted
- Scoped within the block they are in (within the curly bracket {})
- Gives you more control

```js{3-6,12}
// var variables are function-scoped
function foo() {
  if (true) {
    var temp = 'fooooo'
  }
  console.log(temp) // 'fooooo'
}

// let, const variables are block-scoped
function foo() {
  if (true) {
    let temp = 'fooooo'
  }
  console.log(temp) // Uncaught ReferenceError: temp is not defined
}
```

**const** creates **immutable** varibles whereas variables created by let are mutable.

```js
let withLet = 'assigned'
withLet = 're-assigned'
console.log(withLet) // 're-assigned'

const withConst = 'assigned'
withConst = 're-assigned' // TypeError
```

> NOTE ::: If a constant refers to an object or array, the object or array itself can still be changed
