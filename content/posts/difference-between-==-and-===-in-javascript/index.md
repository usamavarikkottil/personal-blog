---
title: "Difference Between == And === in Javascript"
date: 2020-10-20T20:06:28+05:30
draft: false
---

#### Difference between `==` and `===` in javascript

1. Both `==` and `===` are comparison operators, they would compare the values on the left side and in the right side.

2. `==` compares value only, whereas `===` compares value and data type.

```javascript
if("1" === 1 ) {
    alert("Usama Used triple equal signs"); 
    // doesn't pop an alert, because "1"===1 returns false
}

if("1" == 1) {
    alert("Usama Used double equal signs"); 
    // pop an alert, because "1"==1 returns true.
}
```

```javascript
if(1===1) {
    alert("Usama Used triple equal signs"); 
    //  pop an alert, because 1===1 returns true.
}

if(1==1) {
    alert("Usama Used double equal signs"); 
    // pop an alert, because 1==1 returns true.
}

```

```javascript

0 == false   // true
0 === false  // false, because they are of a different type
1 == "1"     // true, automatic type conversion for value only
1 === "1"    // false, because they are of a different type
null == undefined // true
null === undefined // false
'0' == false // true
'0' === false // false

```