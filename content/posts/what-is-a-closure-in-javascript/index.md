---
title: "What are Lexical scoping and Closures in Javascript"
date: 2020-10-12T10:05:00+05:30
draft: false
description: "A brief Introduction to lexical scope and closure in javascript, a beginner's guide"
author: "Usama Varikkottil"
tags : [
    "javascript",
    "closure",
    "lexical scope",
    "javascript interview",
    "coding",
    "programming",
    "computer science"
]
categories : [
    "javascript",
    
]
---


**`NB: This is my personal note. I would not be responsible if you get confused by reading this post.`** 😛

### Lexical Scope in Javascript

A children function has access to the variables declared in the parent function.
```javascript
function outer() {
  let name = 'Usama'; // name is a local variable created by "outer"
  function printName() { // printName() is the inner function.
    console.log(name); // print variable declared in the parent function
  }
  printName();
}
outer();
```
In the above code the variable `name` is declared in the parent function. Since A children function has access to the variables declared in the parent function, the variable is printing from the child function. This is an example for lexical scoping. 


### A closure in Javascript

A closure is a special kind of object that combines two things: a function, and the environment in which that function was created. The environment consists of any local variables that were in-scope at the time that the closure was created.

 A closure is a function having access to the parent scope, even after the parent function has closed.
 This is more confusing than lexical scope. So let's look at the examples given below.

 ```javascript
function outer() {
  let name = 'Usama';
  function printName() { //defining child function
    console.log(name); // display variable declared in parent function
  }
  return printName; // return child fuction (NOT calling function, only returning)
}

let myFunc = outer();// Calling parent function inside new variable "myFunc", after being called parent function forgets variable "name".  
myFunc(); // this results in calling child function, Since child function is returned in the above line of code. The Child function remember variable "name" even after parent function forgets the variable "name". 
 ```

 In the above code, `printName()` function is executed outside of it's lexical scope. But still `printName()` have access to the variable `name`. Here `printName()` is a closure, because it remembers(closes over) the variable `name` from it's lexical scope.

---

 ##### References:

* [Simple explanation of Javascript Closures](https://dmitripavlutin.com/simple-explanation-of-javascript-closures/)

* [MDN Docs Mozilla](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)

* [medium article](https://medium.com/@iampika/javascript-environment-lexical-scope-and-closures-9c8dfaeff73d) 

* [another medium article](https://medium.com/better-programming/a-brief-introduction-to-closures-and-lexical-scoping-in-javascript-8a5866496232)

