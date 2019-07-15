---
title: JavaScript Concept 11 - Callback, Promise and Async/Await
date: 2019-07-15 17:07:14
category: JavaScript
---

## Callback

**What is callback?**

- A function that is to be exceuted after another function
- A function that is passed as an argument to other function

<br>

**When is it needed?**

JavaScript is a single-threaded language, which means that instead of waiting for an event to be finished, JavaScript will keep executing the rest of the events. But sometimes we want to make an event to wait before executing the next one. For example, it takes some amount of time before an API request getting back with the response.

Let's simulate this by using setTimeout.

```js
const APICall = (response, callback) =>
  setTimeout(() => {
    console.log(response)
    callback()
  }, 500)

const makeAPICalls = () => {
  APICall('First', () => {
    APICall('Second', () => {
      APICall('Third', () => {})
    })
  })
}

makeAPICalls()
```

I can print First, Second and Third in order with callback. But imagine that there are hundreds of nested callback functions within a function, which often called **Callback Hell**. It's going to be super ugly and hard to read.

## Promise

Basically, Promise was introduced in an effort to fix the nesting problem in callback hell.

Promise takes two funtions as parameters, **resolve** and **reject**. Make a Promise wrap the whole function and call resolve for the success case and reject if there is an error and return the Promise.

```js
const APICall = response => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log(response)
      resolve()
    }, 500)
  })
}

const makeAPICalls = () => {
  APICall('First')
    .then(() => APICall('Second'))
    .then(() => APICall('Third'))
}

makeAPICalls()
```

This is a **Promise Chain** where the code returns the result of the function and it gets to the next function in the chain. You can check out the resolved value by logging the argument passed to the functions after **then** and error with **catch**.

## Async/Await

- Makes asynchronous code more like synchronous/procedural looking
- Can store the return of asynchronous function in a variable and use it later on.

```js{5,11-13}
const APICall = response => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log(response)
      resolve(response)
    }, 500)
  })
}

const makeAPICalls = async () => {
  let first = await APICall('First')
  let second = await APICall('Second')
  let third = await APICall('Third')

  console.log(first, second, third) // 'First Second Third'
}

makeAPICalls()
```

<br>
<br>

_Sources_

https://codeburst.io/javascript-what-the-heck-is-a-callback-aba4da2deced
https://medium.com/front-end-weekly/callbacks-promises-and-async-await-ad4756e01d90

<br>
<br>
