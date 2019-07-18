---
title: What are Agile, DevOps and CICD
date: 2019-07-18 13:07:95
category: Development
---

## Agile

A process that provides customers with some part of the product or servie instead of making them wait until the product is fully featured which have many advantages:

- Both the company and the customer can get continuous feedbacks along the developing process.
- Companys can cope with fast changing market.

## DevOps

Integrates developers and operations teams in order to improve collaboration and productivity by automating infrastructure, automating workflows and continuously measuring application performance.

**Traditional Way**: writing larage chunks of software over many weeks or months of testing.

**DevOps Oriented** : Write software in small chunks that are integrated, tested, monitored and deployed usually in hours.

## CICD

**CI (Continuous Integration)**

All the codes written by different developers have to be integrated somewhere at some point before go into production server. You don't want to wait until all the codes integrated and go throught unit test at once because this could result in a bunch of bugs at the same time which makes it hard debug. Continuous Integration would help solving the problem.

The idea of this is to integrate the modules as often as your commits. Let's say you are doing five to six commits everyday. Every time the codes are working in your unit test, submit them on the central repository. It will receive the changes and will do the automated proccess of building, testing and providing reports for you.

Commit --> Integration --> Automation Test --> Reports

<br>

**CD (Continuous Delivery and Continuous Deployment)**

<br>

**Continuous Delivery**

Having the integrated code run on the mock server before it goes into production server to make sure the code is running properly and also you can measure the performance of the system in prior to the deployment.

**Continuous Deployment**

Having the integreated code getting tested and deployed onto production server automatically.

## Examples of CICD

**[React JS](https://circleci.com/gh/facebook/react)**

- Has a robust and high visible CICE pipeline.
- The builds and tests run automatically against submitted pull request.

<br>

**Tools:**

- Jenkins
- CircleCI
- TravisCI

<br>
<br>

_References_

https://www.synopsys.com/blogs/software-security/agile-cicd-devops-difference/
https://medium.com/@nirespire/what-is-cicd-concepts-in-continuous-integration-and-deployment-4fe3f6625007
https://www.youtube.com/watch?v=_I94-tJlovg

<br>
<br>
