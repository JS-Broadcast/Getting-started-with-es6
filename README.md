
### [JSBroadcast Official Webpage](http://www.jsbroadcast.com)

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

To simplify this therotical part, variables declared with **let** belong to scope in which they are declared. This can be either **global**, **functional** or **statement** scope. Let's give it a few examples: 



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

// our variables are now accessible in any newly defined scopes inside this function

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


* function expressions can be created the regular way, same as we did with var:

```javascript

let fn = function() {
// function body
}

```

* In terms of ***const***, scoping rules are exactly the same as ***let***, only difference is and it is pretty much self explanatory, const is a constant value and when defined, it cannot be changed, its read-only. 




---

### [03. Getting started with ES6 - class](https://www.youtube.com/watch?v=Hie7noPJORA)

If your first programming is JavaScript and if you have never experienced nor worked with Object Oriented Programming (C, C++, JAVA, C#) etc. you will first want to take a look and certain definitions of what ***class*** is and what it represents. 


> In object-oriented programming, a class is an extensible program-code-template for creating objects, providing initial values for state (member variables) and implementations of behavior (member functions, methods).[1][2] In many languages, the class name is used as the name for the class (the template itself), the name for the default constructor of the class (subroutine that creates objects), and as the type of objects generated by the type, and these distinct concepts are easily conflated.[2]

> When an object is created by a constructor of the class, the resulting object is called an instance of the class, and the member variables specific to the object are called instance variables, to contrast with the class variables shared across the class.


To fully utilise and understand ***class*** keyword, I suggest you to take a look at the [wikipedia article](https://en.wikipedia.org/?title=Object-oriented_programming) and learn a little bit about Object Oriented programming and its concepts.


If you are done with reading, lets go ahead and explain ***class keyword*** in JavaScript world.

Before we get too excited about the class itself, if you are at least semi good JavaScript developer, you are familiar with concept of Objects and Prototypes and with that, you know that classes are not nothing new that happened, ***class keyword*** is just a syntactical sugar over Objects and prototypes which we are familiar with for quiet some time. 

*So does this mean that we won't benefit from this keyword in any other way other then cleaner and "easier to read" code ?*

Well, exactly. ***class*** is basically just allowing us to write much nicer and easier to understand code and instead of creating classes using ***function***, we can finally do it the right way. We usually call features like this *syntactical sugar*.


---


* Anyway lets start writing some code. Before we introduce new class keyword, lets write the class in the old fashioned way. The usual way to create "an old fashioned class" is by creating an object prototype. We do so by creating an object constructor function:


```javascript

function vehicle(maxSpeed, numOfSeats) {

this.maxSpeed = speed;  
this.seats = numOfSeats;

}; 

```

* Now when we have our constructor defined, we can use the ***new*** keyword and create new objects from the prototype we have just created:

```javascript

let ferrari = new vehicle(300, 2);
let jaguar = new vehicle(1900, 19);


```

* Also if we ever wanted, we could add aditional proparties or methods for our newly created object.

```javascript

ferrari.color = 'red';
ferrari.turnOnTheCar = function() {
let on = true;

if(on) {

console.log('brmmmmmm brmmmm');

} else {

console.log('Honeyyyy, where did you leave the keys!');

}
}

```

* This would apply only for that individual object and not to any other e.g. *jaguar*. If we would want to add a new property to our constructor, we would need to do it manually same way we defined the initial ones.

```javascript

function vehicle(maxSpeed, numOfSeats, extraTires) {

this.maxSpeed = speed;  
this.seats = numOfSeats;
this.tires = extraTires;

}; 

```

* We can also add some functionality (methods) to our Prototype (vehicle). 


```javascript

function vehicle(maxSpeed, numOfSeats, extraTires) {

this.maxSpeed = speed;  
this.seats = numOfSeats;
this.tires = extraTires;
this.washMyVehicle = function() {
 // do something
} 

}; 

```

* We can instead use prototype property and add new properties or methods to our initial prototype:

```javascript

function vehicle(maxSpeed, numOfSeats, extraTires) {
// our existing prototype
} 

vehicle.protoype.fixVehicle = function() {
//do something
};

vehicle.prototype.manufactured = 2015;

}; 

```

#### class keyword

Now when have reminded ourselves about ES5 and talked about constructor, object and Prototype, let's see how the new class keyword behaves.

So Classes in JavaScript are functions and just like we did previously, we can define them as class expressions or class declarations.


```javascript
class Person {} // class declaration
let Person = class {} // class expression

// we did this for a long time with functions
function fn () {} // function declaration
let fn = function() {} // function expression

```


Difference between functions and **class** keyword is that functions declarations are hoisted and class declaratios are not. This means that we can't use the class before we define / declare it, like we could do with functions :

```javascript
fn(); // we are invoking the function before its declared
      // but since our function is being hoisted (moved to the top of the file)
      // this will normally work
function fn() {
// some logic
}
```

Scenario with **class** is different and this wouldn't work :

```javascript
let car = new vehicle(); // ReferenceError 

class vehicle {
constructor() {
// some proparties here
}
// class body
}
```

The reason for this limitation is that classes can have an **extends** clause whose value is an arbitrary expression. That expression must be evaluated in the proper “location”, its evaluation can’t be hoisted.

> Each class consists of one-per-class constructor where we define our class proparties and class body where we define class methods. Let's go ahead and explain each one of them.

Before we individually explain each segment of class, lets just see how the class look like:

```javascript
class Computer {
constructor(RAM, CPU) { // one-per-class constructor
this.memory = RAM;
this.processor = CPU;
}

// class body

getSpecs() { // class method
return 'This machine has ' + this.memory + ' of RAM and running on' + this.processor + ' processor.';
}

// .. N of methods

}
```

#### *constructor*

*The constructor method is a special method for creating and initializing an object created with a class.* There can only be one special method with the name "constructor" in a class. A SyntaxError will be thrown if the class contains more than one occurrence of a constructor method.

A **constructor** can use the super keyword to call the constructor of a parent class. - taken from [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/constructor)

```javascript

class pc {
constructor(RAM, CPU) { // one-per-class constructor
this.memory = RAM;
this.processor = CPU;
}

// class body

get_specs() { // class method
return 'This machine has ' + this.memory + ' of RAM and running on ' + this.processor + ' processor.';
}

// .. N of methods

}

class pcExternalDevices extends pc {
constructor(RAM, CPU, external_devices) {
super(RAM, CPU);
this.external_devices = external_devices;

}

specs() {
  return console.log(super.get_specs() + 'It comes with additional ' + this.external_devices);
}

}

let Pentium = new pcExternalDevices('16gb', 'core i7', ['keyboard', 'mouse']);
Pentium.specs();

```

If we take a look at the above example, we notice that we have a parent class called **pc** and a child class called **pcExternalDevices**.

We use **extends** clause to create a subclass of our parent class (existing constructor). Subclasses are usually called *derived* classes, simply because we derive them from the parent class.

As we can see on the example above, we need to call **super()** each time in our derived classes. There are 2 reasons why we need to user **super()**, one is being able to access our parent methods and proparties and second is using *this* keyword.


```javascript
    class Foo {}
    class Bar extends Foo {
        constructor(num) {
            let tmp = num * 2; // OK
            this.num = num; // ReferenceError
            super();
            this.num = num; // OK
        }
    }

```

Also, leaving our subclass without calling super() will also throw an error: 

```javascript
  class Foo {}
    
    class Bar extends Foo {
        constructor() {
        }
    }
    
    let bar = new Bar(); // ReferenceError
```

#### The future of classes

The design maxim for classes was “maximally minimal”. Several advanced features were discussed, but ultimately discarded in order to get a design that would be unanimously accepted by TC39.

Upcoming versions of ECMAScript can now extend this minimal design – classes will provide a foundation for features such as traits (or mixins), value objects (where different objects are equal if they have the same content) and const classes (that produce immutable instances).

Does JavaScript need classes?
Classes are controversial within the JavaScript community. On one hand, people coming from class-based languages are happy that they don’t have to deal with JavaScript’s unorthodox inheritance mechanisms, anymore. On the other hand, there are many JavaScript programmers who argue that what’s complicated about JavaScript is not prototypal inheritance, but constructors [6].

ES6 classes provide a few clear benefits:

* They are backwards compatible with much of the current code.

* Compared to constructors and constructor inheritance, classes make it easier for beginners to get started.

* Subclassing is supported within the language.

* Built-in constructors are subclassable.

* No library for inheritance is needed, anymore; code will become more portable between frameworks.

* They provide a foundation for advanced features in the future (mixins and more).

* They help tools that statically analyze code (IDEs, type checkers, style checkers, etc.).

---

### [04. Getting started with ES6 - Promises](https://www.youtube.com/watch?v=J-yo9u5uVzM)

---

### [05. Getting started with ES6 - Destructuring](https://www.youtube.com/watch?v=VU0ZZkouMaA)


