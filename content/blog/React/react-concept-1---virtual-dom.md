---
title: React Concept 1 - Virtual DOM and the myths around it solved
date: 2019-07-19 15:07:60
category: React
---

## What is the Virtual DOM?

VDOM is a programming concept where an virtual representation of a UI is kept in memory and synced with the real DOM by a library such as ReactDOM.

This approach enables the declarative API of React detect the exact changes of every update: You tell React what state you want the UI to be in, and it makes sure the DOM matches that state.

## Is React "faster than DOM"?

There are some myth out there regarding React and virtual DOM and Dan Abramov's answer for above question was 'NO'.

He said people think there is something in virual DOM but the truth is it is **unnecessarily** updating or reading from DOM nodes in a bad order- normally reading should come first then writing. So it actually can be bad for performance.

## What really happens is:

```
internalInstance.props = newElement.props
```

Nothing fancy, it's just **reassignment**, keeping the props around. "Update" might be a too-much-term for this, he said. The more expensive part is calling React components recursively to learn which elements they render to, and **diffing** child lists.

<br>

### Reconciliation & Commit

All of the above is **reconciliation**. Applying DOM changes, which called **commit**, is usually fast.

**Reconciliation takes longer than commit.** This is why React Team is making reconciliation pausable in Fiber(an ongoing reimplementation of React's core algorithm whose one key feature is the ability to pause, abort, or reuse work as new updates come in).

To recap, Virtual DOM doesn't necessarily make React any faster, because it's doing unnecessary works, but by letting a real DOM only update the changes, it reduces commit phase.

<br>

> React helps create maintainalbe applications, and is **fast enough** for most use cases. <br><br> - Dan Abramov

<br>
<br>

_References_

https://reactjs.org/docs/faq-internals.html
https://github.com/acdlite/react-fiber-architecture
https://twitter.com/dan_abramov/status/842329893044146176

<br>
<br>
