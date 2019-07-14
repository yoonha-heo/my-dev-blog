---
title: JavaScript Concept 9 - Functional Programming & Object Oriented Programming
date: 2019-07-14 16:07:95
category: JavaScript
---

## OOP (Object Oriented Programming)

**Combines a group of related variables and functions into an object.**

A programming paradigm based on the concept of _objects_, which can contain data, known as attributes, and code, often known as methods. With the methods of the same instance(objects have a notion of _this_, which refers to the object itself), we can easily modify the data fields of the object: **altering the state** of the object.

Objects are instances of class. It works like a template which means we can esaily make a new instance of a certain attributes and methods.

```js
class Dog {
  constructor(name, owner) {
    this.name = name
    this.owner = owner
  }
  bark() {
    return 'walf walf'
  }

  change_owner(owner) {
    this.owner = owner
  }

  let dog1 = new Dog('Bori', 'Rossena')
  dog1.owner // 'Rossena'
  dog1.change_owner('Dayoung');
  dog1.owner // Now Bori's owner is 'Dayoung'
}
```

Let's say all dogs have a name and its owner. We can make a new instance of the dog class using new constructor with name and owner parameter. By using the change_owner method, we can also change the state of Bori.

## Benefits of OOP

**1. Encapsulation**
<br>
Reduce complexity + increase reusability
<br>
Using OOP, functions end up having fewer parameters, making them easier to use and maintain.

**2. Abstraction**
<br>
Reduce complexity + isolate impact of changes
<br>
All the complexity is hidden inside. Hiding some of the properties and methods form the outside. It provides simpler interface and reduces the impact of change because we don't have any that touches these methods outside of the containing objects.

**3. Inheritance**
<br>
Eliminate redundant code
<br>
For example, when creating HTML elements intead of defining all the properties and methods, we can define them once in a generic object and utilize it.

**4. Polymorphism (Many form)**
<br>
Refactor ugly conditional statements
<br>
The way of each HTML element is rendered is different from the others. With OOP, we can implement render method in each of these objects and the render method will behave differently depending on the type of the object we are referencing.

## Functional Programming

A paradigm that **focuses on the computation of pure functions**.

- Complete separation between data and functions
- All objects created in functional programming are immutable
- Do not share scope with other objects

## Pure functions

- _Always_ return the same value with the same input value
- There are no side effects that might affect in the change of return value
- Do not alter the passed data

```js
function double(num) {
  return num * 2
}

// The outcome of double only depends on the input num
```

## Benfits of Functional Programming

**1. Predictable**

- gives certain guarantees on what would out come be

<br>

**2. Safe**

- Immutable state
- Needed change in the state, I can just create a new one
- Protect from typos and other error that could happen from mutable state

<br>

**3. Modulaar**

- like a building blocks with small units
- Empowers us to deduplicate the code

## FP vs OOP

**Fucntional Programming**

```js
// Create employees array
let employees = [
  { name: 'Dayoung', salary: 20000 },
  { name: 'Sehyun', salary: 30000 },
  { name: 'Yohan', salary: 25000 },
]

// pure function
// which returns a copy of a single employee with the salary field updated
let change_salary = function(employee) {
  return { name: employee.name, salary: employee.salary + 10000 }
}

// Created a new datatset using the change_salary function
// map returns a new altered dataset
// while each alters the state of the object
let happier_employees = employees.map(employee => change_salary(employee))

happier_employees
// [{name: 'Dayoung', salary: 30000},
// {name: 'Sehyun', salary: 40000},
// {name: 'Yohan', salary: 35000}]
```

**OOP**

```js
// Create Employee class
class Employee {
  constructor(name, salary) {
    this.name = name
    this.salary = salary
  }

  change_salary() {
    this.salary = this.salary + 10000
  }
}

// Create a instance of employee
let employee1 = new Employee('Dayoung', 20000)
employee1.salary // 20000

// Use the each method to change salaray attribute of each employee
employee1.change_salary()

employee1.salary // 30000
```

<br>
<br>

**Sources**
<br>
https://medium.com/@sho.miyata.1/the-object-oriented-programming-vs-functional-programming-debate-in-a-beginner-friendly-nutshell-24fb6f8625cc
https://www.youtube.com/watch?v=pTB0EiLXUC8
https://www.youtube.com/watch?v=FYXpOjwYzcs

<br>
<br>
