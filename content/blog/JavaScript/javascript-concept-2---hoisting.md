---
title: JavaScript Concept 2 - Hoisting
date: 2019-07-02 19:07:32
category: JavaScript
---

## Explain **'Hoisting'**

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
