---
title: JavaScript Concept 1 - Event Delegation
date: 2019-07-01 19:07:15
category: JavaScript
---

## Event Delegation in JavaScript

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

<br>
<br>

_Reference_
https://www.youtube.com/watch?v=MY0UBGX2FtA&t=1025s

<br>
<br>
