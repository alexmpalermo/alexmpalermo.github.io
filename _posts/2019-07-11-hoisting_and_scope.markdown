---
layout: post
title:      "Hoisting and Scope "
date:       2019-07-11 21:54:38 +0000
permalink:  hoisting_and_scope
---


In JavaScipt there are 3 types of variables - var, let, and const. Var variables are able to be resassigned and redeclared,  Let variables are able to be reassigned but not redeclared, and Const variables are not able to be redeclared or reassigned. 

```
var number = 10
var number = 42
console.log(number) // 42
```

```
let number = 10
let number = 42 // SyntaxError
console.log(number)
```

```
const number = 10
const number = 42 // SyntaxError
console.log(number)
```

Var is function scoped and let/const is block scoped. Var declarations, wherever they occur, are processed before any code is executed (aka "hoisting"). Hoisting is when a variable can be used before it has been declared. JavaScript only hoists declarations, not initializations. So, you can access variable x before it is actually declared but its value will be undefined in the first example below.

Input:
```
console.log(x);
var x=5;
console.log(x);
```

Output:
```
undefined
5
```

Let/const cannot be used before they have been declared so it will throw an error. In ES6, you normally would just use let/const instead of var because of this and the fact that they cannot be redeclared. 







