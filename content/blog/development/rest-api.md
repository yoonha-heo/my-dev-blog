---
title: The difference between API and REST API
date: 2019-07-16 18:07:28
category: Development
---

## What is an API?

A way to let software components to talk to each other, and it could be in any form.

<br>

**How do APIs relate to Web Services?**

- Web Servieces are just APIs, but in general, not the other way around.
- REST API = REST web service

## REST API/REST Web Service?

An API that follows the rules of REST specification.

- How software components will talk?
- What kind of messages they will send to each other?
- How requests and responses will be handled?

## What's REST?

REpresentational State Transfer

<br>

**How does HTTP relate to REST?**

- HTTP is an application layer protocol for sending and receiving messages over a network.
- In HTTP, we can use GET method for all sorts of interations.
- REST is a specification that dictates how distributed systems on the web should communicate.
- REST is a certain way to implement and use the HTTP communication.

<br>

**How does The WEB relate to REST?**

- REST is the underlying architecture of the WEB.
- Some developers are breaking the rules.
- It's not the best architectual style but it's still better than doing things arbitrarily.

## The most popular REST rules

1. The method information should be expressed in the HTTP verb.

   ```http
   // Not RESTful
   GET api/users/delete/:userId

   // RESTful
   DELETE api/users/:userId

   ```

2. Scoping information should go in the URI.

   ```http
   DELETE api/users/:userId <-- URI
   ```

## How a RESTful API works?

- It uses proper HTTP methods according to the situation (**GET** for getting data, **POST** for creating data)
- Scoping info(and other data) goes in the parameters part of the URI.
- It uses common data formats(most commonly JSON).
- Communication is stateless.

<br>
<br>

_Source_

https://www.youtube.com/watch?v=FOZtRzY5x8E

<br>
<br>
