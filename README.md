




# Getting Started with ES6
### [Getting Started with ECMAScript 6 - on YouTube](https://www.youtube.com/watch?v=_lGYG_s_yTM&list=PLEKIsm9AjY8LfH5cYnhJE-L5A7NWis6qB)

Repository containing some of the code examples from YouTube courses.


### 01. Getting started with ES6 - Environment 

In order to get started with ECMAScript 6, we need to have our **Environment** installed first. In this video course, we will use [Babel](https://babeljs.io/) which will compile our newly written ES6 into current ES5.

In order to proceed and install [Babel](https://babeljs.io/), we need to have [Node Package Manager](http://www.npmjs.com) installed. NPM comes with installing [nodejs](http://www.nodejs.org) so you can go ahead and [download](http://www.nodejs.org/download) the proper version for your operation system.

After you have NODEJS installed and with it, Node Package Manager, we are ready to install Babel. Simply, open your terminal and type: 

> npm install -g babel

After the installation is completed, you will have babel installed globally on your system and ready for use.

Now, lets go ahead and create a directory where will have our two files, main.js and compiled.js



main.js file is where we will write our code and compiled.js is where our compilation from  ES6 to ES5 will be happen. 

After you have your directory created and both files opened in your IDE / Text Editor, lets start watching for changes on our main.js file and envoke Babel each time when we make a change.

To do so, open your terminal and type:

> babel main.js --watch --out-file compiled.js

Now each time when we make a change and save in our main.js, we will compile our ES6 into ES5 into compiled.js and each time we want to execute our program, we will execute compiled.js.

To execute our program, we simply open up a terminal and type:

> node compiled.js 

If you are done with all the above steps, you are ready to move to the next video where I will talk about new way of declaring variable using new ES6 keyword **let**.

---

### [02. Getting started with ES6 - let](https://www.youtube.com/watch?v=l2rHcpLAhsw)

> Before starting with reading whats coming after, please take a look at [JavaScript Declarations Hoisting](http://www.w3schools.com/js/js_hoisting.asp) so you can understand how JS "compiler" hoists the declarations. This is crucial to know in order to fully understand the content below and var vs let vs const

> Another good article to take a look is [Original Mozzila Developer Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)


 * **let** allows you to declare variables that are limited in scope to the block, statement, or expression on which it is used. This is unlike the var keyword, which defines a variable globally, or locally to an entire function regardless of block scope.

 * If we take a look at the "official" definition of let, we can pretty much understand how **let** works. If we compare *var* vs *let* we can pretty much come to a conclusion that the only difference between those two is scoping. *var* is scoped to the nearest function block (or global if outside a function block), and let is scoped to the nearest enclosing block (or global if outside any block), which can be smaller than a function block.

To simplify this therotical part, variables declared with **let** belong to scope in which they are declared. This can be either **global*, **functional** or **statement** scope. Let's give it a few examples: 



* In the global scope, declaring variables either with *let*, *var* or *const* makes no difference. They end up beloging to the global scope and available to all functions afterwards.
```javascript
var x = 5;
let y = 6;
const z = 7;
```
All of the above are now globally scoped, therefor, there aren't any differences when scope is concerned. This also applies to pretty much any scope if they are declared at the top (top of statement, loop, function). 

```javascript
function fn() {
var x = 5;
let y = 6;
const z = 7;

// accesible afterwards in any function statements

}

```

In other cases whatsoever, those behave differently. While let and constant are equivalent in terms of scope rules, their only difference is that constant is read only variable, while let obviously it is not.


* If we declare variable x with let in the function scope and declare another variable with the same name in *if statement* scope, those two will be two separate variables belonging to their **own** scopes.

```javascript
  function fn() {
      let x = 5; // this x belongs to function scope
      if(x > 4) {
     
      let x = 6; // this x belongs to if statement scope and therefor, it is a separate variable
      console.log(x); // 6
      }
    console.log(x); // 5; This is the variable declared at the top of our function
  }

---

    function fn() {
      var x = 5;
      if(x > 4) {
      var x = 6; // x is now 6
      console.log(x) // 6
      }
      console.log(x) // 6; X declared at the top of the function got redefined in the if statement
    
  }

```

* Taking a look at the example above shows pretty much what variable block scoping is. If you check the example with var, you will notice that our x got redefined aka redeclared and got its new value, while using let simply ignores that and keep its variable declaration bound to its scope. In the example of let, we are having two variable in the same function declared with the same name and yet, they behave corresponding to the scope they have been defined / declared in.

* Also, if you have you clicked the article [JavaScript Declarations Hoisting](http://www.w3schools.com/js/js_hoisting.asp) you will notice that ***let*** behaves differently and that variables declared with it are hoisted at the top of their current block and not at the top of the place of its current global scope. 

* In terms of ***const***, scoping rules are exactly the same as ***let***, only difference is and it is pretty much self explanatory, const is a constant value and when defined, it cannot be changed, its read-only. 

* 


---

### [03. Getting started with ES6 - class](https://www.youtube.com/watch?v=Hie7noPJORA)

---

### [04. Getting started with ES6 - Promises](https://www.youtube.com/watch?v=J-yo9u5uVzM)

---

### [05. Getting started with ES6 - Destructuring](https://www.youtube.com/watch?v=VU0ZZkouMaA)


