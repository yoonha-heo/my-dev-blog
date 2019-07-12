---
title: JavaScript Concept 2 - Scope and Closure
date: 2019-07-12 14:07:05
category: TIL
---

## 1. What is Scope?

A scope in JavaScript defines what variables are accessible. There are two kinds of scope - **global scope** and **local scope**

<br>

**Global scope (Not advised)**

When a varible is declared outside all functions or curly brackets.
There's a chance of naming collisions if two or more variables are declared with the same name using let or const.

```js
// Declaring variables with the same name using let(const) in global scope

let greeting = 'hi'
let greeting = 'hello' // Error : Already been declared
```

Though it's possible to do so when you declare variables with var, it is still not advised because this will make the code hard to debug.

```js
// Don't do this
// It will mess up the code, hard to debug

var greeting = 'hi'
var greeting = 'hello' // doesn't throw error

console.log(greeting) // 'hello'
```

<br>

**Local Scope**

When variables are accessible only in a specific part of the code
There are two kinds of local scope: **function scope** and **block scope**.

## 2. What does it mean that JavaScript uses lexical scoping?

Inner variable is not accessible from outside but anything that is defined outside is automatically available inside the function. This behavior is called **lexical scoping**.

## 3. Explain some examples of closure

```js{8}
// The simplest example

let passed = 3

let addTo = function() {
  let inner = 2
  console.log(inner)
  return passed + inner // using a variable outside function
}

console.log(addTo()) // 5
```

Any functions where you are using variables outside function are **closures**.

In order to execute addTo function it will look through the varibles it needs. Since _passed_ is not defined inside the function, it will look at the scope outside function. It would keep going up until it founds the variable.

Let's look at the another example.

```js{9}
let addTo = function(passed) {
  let add = function(inner) {
    return passed + inner
  }

  return add
}

let addToThree = addTo(3) // preserves value inside
console.log(addToThree(4)) // 7
```

addTo(3) function preserves 3 value inside the function as closure. This means I can create unlimited number of functions using closure. It keeps the varible it needs to execute.

<br>

> Conclusion : Closure is a **function with preserved data**

<br>
<br>

_References_

https://www.youtube.com/watch?v=71AtaJpJHw0
https://css-tricks.com/javascript-scope-closures/

<br>
<br>
