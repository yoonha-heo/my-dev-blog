---
title: JavaScript Concept 7 - == and ===
date: 2019-07-07 19:07:05
category: JavaScript
---

## What's the difference between == and === ?

**==**
<br>
Checks for **equality**
<br>
<br>
**===** <br>
Checks for **equality and type**
<br>
<br>
== in JavaScript sees both null and undefined as having no value eventhough they have different types

```js
// checkout this badness
let foo // undefined
let temp = null // null

// compare the two
console.log(foo == temp) // true(boolean), what??
```
