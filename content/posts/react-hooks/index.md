---
title: "React Hooks - useState"
date: 2020-11-18T09:00:11+05:30
draft: false
---

Hooks let you use state and other React features without writing a class. Hooks are A set of functions that provide a direct API to methods we access on Component instances. 

#### useState in React
Look at this counter app example.

```jsx
import React, { useState } from 'react';

function Counter() {

  // Declare a new state variable
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Number of Clicks =  {count} </p>
      <button onClick={() => setCount(count + 1)}>
        Click here</button></div>
  );
}
```

The `useState` hook provides a current state value and a way to update it. We call it inside a function component to add some local state to it. The only argument to `useState` is the initial state. And it is the default value. That value can be any type.
(In our example above, the argument is 0. That is because we want to start our counter from zero.)

`useState` returns a pair: the current state value and a function that lets you update it.

* Hooks don't work inside classes, but Hooks help us to use React without classes.

* There are several hooks other than `useState`. [Hooks API Reference](https://reactjs.org/docs/hooks-reference.html)