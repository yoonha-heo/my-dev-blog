---
title: 'JavaScript Concept Interview Questions and Answers 1'
date: 2019-07-10 21:07:07
category: 'TIL'
---

## 1. Explain event delegation

JS event listeners fire not only on a single DOM element but on **all its decendants**. For example, if you add event listeners to ul, you're actually adding event listeners to all of children elements inside ul as well. This happens through a process called **event bubbling**

event.target : The actual element that triggered event<br>
event.currentTarget : The element with the listener attached

```js
function handleChange(event) {
  // when name changes
  console.log(event.currentTarget) //form tag
  console.log(event.target) //name input tag
}

let el = document.getElementById('form')
el.addEventListener('change', handleChange)

<form id="form">
  <div class="input-group">
    <label class="control-label" for="Name">Name</label>
    <input type="text" id="Name" name="Name" placeholder="John Doe" />
  </div>
  <div class="input-group">
    <label class="control-label" for="Email">Email</label>
    <input type="text" id="Email" name="Email" placeholder="example@gmail.com" />
  </div>
</form>
```

## 2. Explain why the following doesn't work as IIFE

```js
function foo() {
    // i pity this code
}();
```

In fact, this is how JS reading IIFE (hoisting applied)

```js
function foo() {

}

(); // as if you wrote it on separate lines
```

You can make it work simply by putting parentheses around it. In this way, you can make the function at an expression.

```js
;(function foo() {})()
```

Why would I ever use one? => **To control variable scope**

```js
;(function foo() {})()

console.log(foo) // referenceError: foo is not defined
```

The variables inside of the foo function will only be availble inside the function not outside of the function, which can let us use dumb(?) and plain naming conventions in our application.

## 3. The difference on the usage of 'Definition' and 'Expression'

```js
definition() //'I am definition'
expression() // Uncaught TypeError: expression is not a function

function definition() {
  return 'I am definition'
}

var expression = function() {
  return 'I am expression'
}
```

Expressions result in a value even if just "undefined"
Definition creates sort of like a reference but it's not an actual value so you can't run it

```js
function definition() {
  return 'I am definition'
}

let expression

definition()
expression()

expression = function() {
  return 'I am expression'
}
```

## 4. Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?

It's because you can't predict the future.

- Reduce collision within your scope
- Maintain independence
- Easier to write your own code when it's self-contained

## 5. Explain **'Hoisting'**

All variables using var are declared at the top of any given function scope whether you like it or not(includes function declartions)

```js
function hoist(country) {
  if (country === 'Korea') {
    var greeting = '안녕'
  } else {
    var greeting = 'hello'
  }
  return greeting
}
```

var declaration **hoisted** to top. Linters don't like this but browsers don't mind. This works perfectly fine in the browsers.

```js
function hoist(country) {
  var greeting
  if (country === 'Korea') {
    greeting = '안녕'
  } else {
    var greeting = 'hello'
  }
  return greeting
}
```

So technically, this one works too.

```js
function hoist(country) {
  if (country === 'Korea') {
    greeting = '안녕'
  } else {
    greeting = 'hello'
  }
  var greeting

  return greeting
}
```

This is pretty absurd and this is reason why people say that they hate JavaScript. This has kind of been addressed with the introduction of **const** and **let** in es6.

## 6. What's the difference between var, let, and const?

**let & const**

- Not hoisted
- Scoped within the block they are in
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

## 7. What's the difference between a varible that is: null, undefined or undeclared?

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

null has a value. Its value is null which is a **nothing** value.
Can be used in a situation where you need to zero out of value.

```js
const valueIsNull = null

console.log(valueIsNull) // null
```

check for undefined

```js
let foo

// bad idea
console.log(typeof foo) // undefined as a string
console.log(typeof temp) // undeclared, but also returns 'undefined'

// preferred way
console.log(foo === undefined) // boolean true
```

check for null

```js
const foo = null

// terrible idea
console.log(typeof foo) // object

// preferred way
console.log(foo === null) // boolean true
```

## 8. What's the difference between == and === ?

**==** checks for **equality**
**===** checks for **equality and type**

== in JavaScript sees both null and undefined as having no value eventhough they have different types

```js
// checkout this badness
let foo // undefined
let temp = null // null

// compare the two
console.log(foo == temp) // 'true' what??
```

<br>
<br>

_References_

https://www.youtube.com/watch?v=MY0UBGX2FtA&t=1025s
https://2ality.com/2015/02/es6-scoping.html

<br>
<br>
