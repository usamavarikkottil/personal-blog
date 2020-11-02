---
title: "Difference Between Null and Undefined in Javascript"
date: 2020-10-20T20:23:47+05:30
draft: false
---

#### The Differences between `null` and `undefined` in Javascript

* They both represents empty value. But when you define a variable and not assign a value to it, it automatically gets place a value `undefined`. We don't have to do it, the javascript will automatically do it for us.
 And we can assign `null` into a variable ourselves. 

* `typeof(undefined)` returns "undefined", but `typeof(null)` returns "object".
* `null !== undefined`, but `null == undefined`.