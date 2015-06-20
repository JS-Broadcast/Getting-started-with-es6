# Getting Started with ES6
### [Getting Started with ECMAScript 6 - on YouTube](https://www.youtube.com/watch?v=_lGYG_s_yTM&list=PLEKIsm9AjY8LfH5cYnhJE-L5A7NWis6qB)

Repository containing some of the code examples from YouTube courses.


### 01. Getting started with ES6 - Environment 

In order to get started with ECMAScript 6, we need to have our Environment installed first. In this video course, we will use [Babel](https://babeljs.io/) which will compile our newly written ES6 into current ES5.

In order to proceed and install [Babel](https://babeljs.io/), we need to have [Node Package Manager](http://www.npmjs.com) installed. NPM comes with installing [nodejs](http://www.nodejs.org) so you can go ahead and [download](http://www.nodejs.org/download) the proper version for your operation system.

After you have NODEJS installed and with it, Node Package Manager, we are ready to install Babel. Simply, open your terminal and type: 

 * npm install -g babel

After the installation is completed, you will have babel installed globally on your system and ready for use.

Now, lets go ahead and create a directory where will have our two files, main.js and compiled.js



main.js file is where we will write our code and compiled.js is where our comiled ES6 to ES5 will be located. 

After you have your directory created and both files opened in your IDE / Text Editor, lets start watching for changes on our main.js file and envoke Babel each time when we make a change.

To do so, open your terminal and type:

 * babel main.js --watch --out-file compiled.js

Now each time when we make a change and save in our main.js, we will compile our ES6 into ES5 into compiled.js and each time we want to execute our program, we will execute compiled.js.

To execute our program, we simply open up a terminal and type:

 * node compiled.js 


