---
title: JavaScript Concept 10 - ES5 vs ES6
date: 2019-07-15 13:07:81
category: JavaScript
---

## Arrow function

We can now keep our code clear and short with arrow function.

**ES5**

```js
function sayHello(name) {
  return 'hello ' + name
}
```

**ES6**

```js
const sayHello = name => `hello ${name}`
```

When passing a single parameter, you can ditch the parenthesis around the parameter. Plus, arrow function provides us with **implicit return if there's no block**.

```js
// returns 'Hi Dayoung'
// no block means implicit return

;(name => 'Hi ' + name)('Dayoung')
```

```js
// returns defined
// explanation: explicit return in block exists

;(name => {
  'Hi ' + name
})('Dayoung')
```

**this in arrow function**

this refers to the **parent scope** in arrow function.

```js{3-6}
// this in arrow function
let obj = {
  multiplier: 2,
  doubleTheNums() {
    return [1, 2, 3].map(num => (num = num * this.multiplier))
  },
}

obj.doubleTheNums() // [2, 4, 6]
```

## Object Manipulation

**Spread/Rest Operator**

We can now use spread operator to merge objects instead of assign method.

```js
// es5
var obj1 = { a: 1, b: 2 }
var obj2 = { a: 2, c: 3, d: 5 }
var obj3 = Object.assign(obj1, obj2)

// es6
const obj1 = { a: 1, b: 2 }
const obj2 = { a: 2, c: 3, d: 5 }
const obj3 = { ...obj1, ...obj2 }
```

<br>

**Destructuring Assignment**

In ES5, we had to assign the values separately if you wanted to store one or more variables from an object.
With ES6 we can do this in one beautiful line.

```js
// es5
var obj1 = { a: 1, b: 2, c: 3, d: 4 }
var a = obj1.a
var b = obj1.b
var c = obj1.c
var d = obj1.d

// es6
const obj1 = { a: 1, b: 2, c: 3, d: 4 }
const { a, b, c, d } = obj1
```

<br>

**Object Literals**

When creating an object, you can make a use of already exisiting variable that is named the same as the key.

```js
const a = 1
const b = 2
const c = 3
const d = 4
const obj1 = { a, b, c, d }
```

## Exporting & Importing Modules

More intuitive exporting and imporing module syntax

**ES5**

```js
// exporting
var myModule = {
  a: 1,
  b: function() {
    console.log('es5')
  },
}

module.exports = myModule

// importing
var myModule = require('./myModule')
```

**ES6**

```js
// exporting
const myModule = {
  a: 1,
  b: () => {
    console.log('es6')
  },
}

export default myModule

// importing
import myModule from './myModule'
```

We have to import the whole module that's been exported with _export default_.
If you want to export and import child variables or modules separately, you can make it work like this.

```js
// exporting
export const a = 1
export const b = () => {
  console.log('es6')
}

// importing
import { a, b } from './myModule'
```

## Class

The new way to implement OOP in JavaScript besides constructor function and prototype, _Class_ looks like this:

```js
class Cat {
  constructor(name, treat) {
    this.name = name
    this.treat = treat
  }

  sayMeow() {
    return 'Meow Meow'
  }
}

let myCat = new Cat()
myCat.sayMeow() // 'Meow Meow'
```

You can also extends classes by using the **extends** keyword, which enables you to inherit attributes and methods of parent Class.

```js
class Horse {
  constructor(name) {
    this.name = name
  }

  run() {
    return 'Running to the destination'
  }
}

class FlyingHorse extends Horse {
  constructor(name) {
    // super keyword calls functions on a parent object
    super(name)
  }

  fly() {
    return 'Flying to the destination'
  }
}
```

<br>
<br>
_Sources_

http://developmentr.com/javascript/2015/12/31/javascript-es6.html#classes
https://medium.com/recraftrelic/es5-vs-es6-with-example-code-9901fa0136fc

<br>
<br>
