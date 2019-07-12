---
title: JavaScript Concept 6 - Null Undefined Undeclared
date: 2019-07-06 19:07:65
category: JavaScript
---

## What's the difference between a varible that is: null, undefined or undeclared?

**Undeclared**

```js
const foo = foo1 + 1

// foo1 is undeclared
```

**Undefined**

It's declared but it hasn't been assigned with any values.

```js
let foo
let obj = {}
let arr = [1, 2, 3]
const temp = function() {
  // don't return anything
}

console.log(foo, obj.name, arr[5], temp()) // undefined
```

**Null**

Null has a value. Its value is null which is a **nothing** value.
Can be used in a situation where you need to zero out of value.

```js
const valueIsNull = null

console.log(valueIsNull) // null
```

**Check for undefined**

```js
let foo

// bad idea
console.log(typeof foo) // undefined as a string
console.log(typeof temp) // undeclared, but also returns 'undefined'

// preferred way
console.log(foo === undefined) // boolean true
```

**Check for null**

```js
const foo = null

// terrible idea
console.log(typeof foo) // object

// preferred way
console.log(foo === null) // boolean true
```
