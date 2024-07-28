# Javascript Interview Question and Answer

### 1.What is Scope?

Scope is the accessibility of variables, functions, and objects in some particular part of your code.

Javascript has 3 type of scope
1.Block Scope
2.Function Scope
3.Global Scope

**1.Block Scope**
varibale declare inside a {curly bracket} block cannot be accsed from the outside the block

```js
let a = 20;
if (a == 20) {
  let b = 30;
  let c = 40;
  console.log(a); //20
  console.log(b); // 30
  console.log(c); // 40
}
console.log(b); // b is not defined reference error
```

**2.Global Scope**
variable declared globally (outside any function) which can be accessed from anywhere in a javascript program

```js
let a = 20;
if (a == 20) {
  console.log(a); // 20
}
console.log(a); //20
```

**3.Function Scope**
variable declared inside a function can only be accessed inside that function

```js
function Saur() {
  let a = 20;
}
console.log(a); // a is not defined reference error
```

**var variable is not a block scope**

```js
if var a = 20
if(true){
    console.log(a); //20
    var b = 40;
    console.log(b) //40
}
console.log(b) //40

```

**var is a function scope**

```js
function saur() {
  var a = 20;
}
console.log(a); // a is not defined
```

### 2.different between var,const,let ?

var is globale scope.
let and const are block scope.

let and const are hoisting.
var is not hoisting.

**var**
if we declare a varibale from var then we can also declare it again with the same name and if we want to re-assign its value then we can do that also

```js
var a = "Sau";
var a = "Sach";
console.log(a); //Sach
```

**let**
if we declare a variable from let then we can not declare it again with the same name but re-assign it's value

```js
let a = 20;
let a = 30; //error can not declare again

let a = 20;
a = 30;
console.log(a); //30
```

**const**
if we declare a variable from const, then we can either declare it again nor can re-assign its value.

```js
const a = 20;
const a = 40;
//syntax error

const a = 20;
a = 40;
//syntax error
```

### 3. Hoisting

Hoisting is the default behavior of moving all the declaration at the top of the scope before code execution.

> Akshay Saini

Hoisting in a javascript is a process in which all the variable,function and class defination are declared BEFORE excecution of the code.

variable initialized to undefined when they are declared.
function defined as it is.

they are declared in _memory location phase_ in the memory component of execution context, so we can use them even **before** theyare declared.

undefined means variable has been declared but value is not assigned.
Non-defined means variable not declared.

variable can be declared after in has been used othe word.
variable can be used before It has been declared.

var is hoisted
let and const does not allow hositing.

**Example :**

```js
var x = 9;
function getName() {
  console.log("Hello Saurabh");
}
console.log(x); // 9
console.log(getName()); //Hello Saurabh
```

```js
console.log(x); // undefined
console.log(getName()); // Hello Saurabh
var x = 9;
function getName() {
  console.log("Hello Saurabh");
}
```

```js
getName(); // Uncaught TypeError: getName is not a function
console.log(getName);
var getName = function () {
  console.log("Namaste JavaScript");
};
//code won't execute as the first line itself throws an TypeError
```

### 3. Closures

A closures is a function that has access to its outer function scope even after thr function has returned
or
A closure is combination of function bundled together with reference to its surronding state(the kexical enviroment)
or
closure are the function that have access to the variable that are present in there scope chain.

![Screenshot of a comment on a GitHub issue showing an image, added in the Markdown, of an Octocat smiling and raising a tentacle.](/closures.png)

### 4. Call back Function

A callback function is a function passed as an argument to another function. This function is to be executed after some operation has been completed.

```js
function greet(name, callback) {
  console.log("Hello " + name);
  callback();
}

function sayGoodbye() {
  console.log("Goodbye!");
}

greet("Alice", sayGoodbye);

// Output:
// Hello Alice
// Goodbye!
```
