---
title: "Difference Between Var and Let in Javascript"
date: 2020-10-11T12:27:07+05:30
draft: false
description: "Beginner's friendly guide, The difference between var and let keywords in javascript, Interview guide for beginners"
author: "Usama Varikkottil"
tags : [
    "javascript",
    "let var",
    "let in javascript",
    "javascript interview",
    "coding",
    "programming",
    "computer science"
]
categories : [
    "javascript",
    
]
---

### var and let

var and let are two keywords used to declare variables in Javascript. Even though most beginners know these two keywords exist, we struggle with finding the difference between them. So let's look at the difference between these keywords.

##### Declaring variables Example

```javascript
var humanOne = "usama";
let humanTwo = "jaba";

console.log(humanOne); //Output: usama
console.log(humanTwo); //Output: jaba
```

#### Declaring variables in for loop (`let` and `var`)

```javascript
for (let i=0; i<10; i++){
    console.log(i);//Ouput will contain numbers from 0 to 9
}
console.log(i);// This will throw an error.
```

In the above example, the ```console.log``` inside the ```for``` loop block will print numbers from zero to nine on the console. However, the last `console.log` code outside `for` loop block will throw an error, Since the variables declared using `let` keyword is only accessible in the block where it is declared. In this case, the variable `i` is only accessible inside the `for` loop block.

##### Now let's change the `let` with `var` on the above code.

```javascript
for (var i=0; i<10; i++){
    console.log(i);//Ouput will contain numbers from 0 to 9
}
console.log(i);// Output: 10
```

In the above example, `i` is accessible outside the `for` loop block. Because we are using the keyword `var` to declare a variable `i`. Here the first `console.log` code will print the numbers from 0 to 9. And after printing the number 9, the value of the `i` becomes 10. Then the condition for `for` loop fails and it will jump out from the `for` loop. Thus execute the last line of code `console.log(i)`. Which will then print the number 10 on the console.

#### The Scope of the `var` variable in a function

The variable declared using the `var` keyword inside a function is accessible throughout that function, but not outside the function. Look at the below example.

```javascript
function count() {
    for (var i = 0; i < 10; i++) {
        console.log(i); // Output: print numbers from 0 to 9
    }
    console.log(i); // Output: 10
}

count(); // calling function
console.log(i); //Output: Uncaught ReferenceError: i is not defined
```

The last line of the above code will throw an error since `var` variables are only accessible inside the function where it is declared.

#### Notes:

* `var` is there in javascript from the beginning, but `let` and `const` are introduced recently in es6.
* `var` is function-scoped, while `let` and `const` are block-scoped.
* Global variables declared using the `var` keyword would automatically get attached to the browser `window` object. Whereas `let` prevents it.
* Variable defined with `var` gets hoisted at the top of it's function. Variable defined using `let` and `const` doesn't gets hoisted.
* We can redeclare `var` variables as many times as we want, while `let` cannot be redeclared.
    ```javascript
    var humanOne = "usama";
    var humanOne = "new Usama"; // This is OK

    let humanTwo = "jaba";
    let humanTwo = "new Jaba"; // Throws an error.
    ```
* We can re-assign a new value to `var` and `let` variables. But a new value cannot be re-assigned to the `const` variable.

    ```javascript
    let personOne = "usama";
    personOne = "new Usama";
    console.log(personOne); // Output: new Usama

    const personTwo = "jaba";
    personTwo = "new jaba"; //Uncaught TypeError: Assignment to constant variable.
    console.log(personTwo);

    ```

    * However, `const` does allow us to change the properties of an object.
        ```javascript
        const Usama = {
            name: "usama v",
            age: 20
        }

        Usama.age = 19;
        console.log(Usama); // Output: {name: "usama v", age: 19}
        ```

* Use `const` and `let` almost every single time when you declare variables unless you have a very specific case using `var`.

#### For more information watch these videos



{{< youtube 9WIJQDvt4Us >}}

---

{{< youtube XgSjoHgy3Rk >}}
