---
title: JavaScript Concept 5 - Statement(Definition) and Expression
date: 2019-07-05 19:07:88
category: JavaScript
---

## The difference on the usage of 'Definition' and 'Expression'

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

## Explain why the following doesn't work as IIFE

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
