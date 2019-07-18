---
title: SQL vs NoSQL- Which one you might want to use
date: 2019-07-18 16:07:56
category: Development
---

# What is SQL?

_Structured Query Language_ with which you can retrieve/insert/update/delete the data you need from database.

## Relational Database

A database which works with certain assumptions or in a certain way and it supports the sql. Such database works with tables. Have to be precise with a **clear schema** of which data can go into a table which has own fields(columns) and records(rows). It can't hold more fields than the ones we defined for the table.
All records have to follow this schema. You typically don't only work with one table but instead with **multiple tables which are related**.

## Non Relational Database

In Non Relational Database, there's **no schema** applied therefore you can be **more flexible** regarding the data format. Generally there are no relations in no sql world. Putting all the information in one place. Have less relation merging going on, have super fast end efficient queries therefore. But the disadvantages is that you have some duplicates in data.

## Then which one is a winner?

There's no clear winner. It really depends on the kind of application you are building and the kind of data you are storing. With really big applications or businesses you typically use both.

<br>

**SQL**

- Data uses Schema(predictable layout)
- when there're many updates in data, it's useful
- Vertical Scaling (improve server capacitiy / hardware) available

<br>

**NoSQL**

- Schema-less(flexible)
- Useful when there're many readings
- Horizantal Scaling (add more servers and merge data into one database) available

<br>

SQL will be a better choice for the business that has pre-defined structures such as accounting system, inventory monitoring system or when running on legacy systems.

<br>

NoSQL will be a strong choice for any businesses that have rapid growth, no clear definition for schema or when the schema continues to change in cases like real-time analytics or content management systems.

<br>
<br>

_sorces_

https://www.xplenty.com/blog/the-sql-vs-nosql-difference/?source=post_page---------------------------
https://www.youtube.com/watch?v=ZS_kXvOeQ5Y&t=1121s

<br>
<br>
