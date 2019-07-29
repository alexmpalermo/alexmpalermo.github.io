---
layout: post
title:      "Hoisting and Scope "
date:       2019-07-11 17:54:39 -0400
permalink:  hoisting_and_scope
---

**SCOPE:**

In JavaScipt there are 3 types of variables - var, let, and const. The differences between these variables will be discussed below. Scope is basically the space where something will reach. Every function creates its own scope, and any variables or functions you declare inside of the function will not be available outside of it.

In this case: 

```
function helloFunc() {
     let hello = "World!";
     console.log(hello);
}
	 
console.log(hello); // Uncaught ReferenceError: hello is not defined
```
	 
The scope of 'hello' is inside of the function, so if you tried to use it somewhere else it won't work. 

Variables can also be block-scoped, meaning they only are available inside the block. Let/const are block-scoped but var is not. 

```
if (true) {
  var n = 42;
}
 
n;
// => 42
```

but...

```
if (true) {
  let x = 12;
	const g = 10;
}
 
x;
// => Uncaught ReferenceError: x is not defined

g;
// => Uncaught ReferenceError: g is not defined
```

Variables without using the let,const, or var keywords are globally-scoped. This means they are accessible anywhere within the code. This example from Learn Co explains it very well.

```
function bankAccount () {
  secretPassword = 'il0v3pupp135';
 
  return 'bankAccount() function invoked!';
}
 
bankAccount();
// => "bankAccount() function invoked!"
 
secretPassword;
// => "il0v3pupp135"
```


Problems demonstrated in the examples above with globally-scoped and var variables can be avoided by just using let and const variables. 

**HOISTING:**

In ES6, var has become somewhat obsolete (due to scoping and hoisting problems) and let/const are the only variables you should be using. Hoisting refers to when declarations appear to be brought to the top of the current scope . In JavaScript, hoisting only applies to variable declarations; not variable assignments. In other words, you can access the variable even if it is placed after the line of code being executed, but it will return undefined. 

For example, when you have something like this:  

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

It logs out "undefined" first because x has been declared (gets hoisted to the top), but the x=5 assignment doesn't get hoisted. It is as if you wrote ```var x;``` and that's it. The second line of code logs 5 because the variable has been declared and assigned before it runs that line. To avoid errors like this, just make sure you declare all of your functions/variables at the top of their scope. 

Let/const cannot be used before they have been declared so it will throw an error, this is why these variables are a much safer choice to use instead of var. 


```
var number = 10
var number = 42
console.log(number) // 42
```

```
let number = 10
let number = 42  // SyntaxError
console.log(number) // 10
```

```
const number = 10
const number = 42 // SyntaxError
console.log(number) // 10
```









