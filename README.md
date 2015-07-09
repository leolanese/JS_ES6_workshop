# ES6 workshop
## The road to ECMAScript 6: New solutions for old JS problems


``ECMA Script 6 is already here``, and more and more of the production libraries and frameworks we use to create our applications are going to be written using this new version of JavaScript. Instead of waiting on the sidelines, ``we can start using ES6 now`` with the help of transpilers/shim, and enjoy many of the benefits without worrying about browser compatibility.


## Goal of the Workshop:
1. Introduction to new ES6 features.
2. How to use these features today.


Further information:

Looking for   | Go to
------------- | -------------
Sources          | [View](https://www.google.com) 
GITHUB        | [GITHUB](https://github.com/sirwilliam/ES6_workshop.git) 
Twitter        |[LeoLanese Twitter](https://twitter.com/leolaneseltd) 

----
Topics:

1. What is ES6? 
2. Key Features in ES6
3. Should I Use ES6 Now or Wait?. How to start using ES6 now?
4. What next?

----
# 1- What is ES6?: 

![alt text](https://farm8.staticflickr.com/7306/16407404782_8b9c57eab3_m.jpg "EcmaScript6")

### "ES6 will change the way you write JS code."
To tell you the true, when I read this quote it’s scared me a little bit, thinking old code old knowledge could go to the bin.
Reality check: ``**ES6 is an enhancement of ES5.** ES6 brings new features, solve few problems and it can be partially or complete incorporated to our code`` and make things easy to understand.

> ES6 Goal: To be a better language

### Why we want to learn ES6?
We are developers, we are progressive. **We want to learn the latest things so we can build the best applications possible.**
We will be ready, our product will be future proof and as a developer we will be more marketable as a coder in the industry.

A large number of the top libraries that are building these days are all going to be written in ES6 in the near future, ES6  will positioning an step ahead and we will be ready for AngularJS 2, Ember 2

![alt text](http://svgporn.com/angular.svg "EcmaScript6")
### AngularJS 2:
**AngularJS2 it’s going to be a big deal.**
``If you worry to get ready to AngularJS2, about being ready from a knowledge standpoint there are some new things that you should know about.``

### What can we do right now in order to be up to date when AngularJS 2 comes?
If you want to be ready for AJS2 we can start learning ES6, and **we’ll be ahead of the game**.
We can be ready and prepared focusing on one thing in particular: ES6

### Do I need to migrate my javaScript code to ECMAScript 6?
``**There is no need**: ECMAScript 6 is a superset of ECMAScript 5. ``Therefore, all of your ES5 code is automatically ES6 code. How exactly ES6 stays completely backwards compatible

---
# 2- Key Features in ES6:

![alt text](https://farm8.staticflickr.com/7306/16407404782_8b9c57eab3_m.jpg "EcmaScript6")

01. Block Scope
02. Arrow functions
03. Block-level scope
04. Classes
05. Modules
06. New utility methods for Strings and Arrays
07. Destructuring
08. Generators
09. Map
10. Promises
11. Rest parameters
12. Set
13. Template Strings

## 01. Block Scope: let and const
### let()
Up to ES6 variables are always function scoped: So, ``no matter where you declare your variable, these are going to be hoisted on the top of the scope.``

Variable declared using let will only be available in the ‘current block’ instead of the ‘entire function’ when using var.
The let keyword allows you to define variables within the scope of the block (block scoping).

>  Don't replace let for var


#### let w/function:
[Ej1: let w/function](http://www.es6fiddle.net/ibt75xzh/)

#### let w/looping:
[Ej2: let w/looping](http://www.es6fiddle.net/ibt7tkvh/)


### const()
We will be able to create constants and make sure its value won’t be changed
[Ej1: const](http://www.es6fiddle.net/ibs2z9yg/)


---
## 02. Arrow functions: =>
1.1 Providing a work around to: ‘that = this’ or ‘bind()’
1.2 With a more compact version of an ‘anonymous function syntax’.

[Ej1: Example](http://www.es6fiddle.net/ibtfr5fk/)

[Ej2: ES5 Vs. ES6: ES5](http://jsfiddle.net/leolanese/uz9x15x7/)

[Ej2: ES5 Vs. ES6: ES6](http://www.es6fiddle.net/ibtfwm70/)


---
## 03. Block-level scope: {}
### This creates a Temporal Dead Zone

---
## 4- Classes and inheritance: class, extends, 
Instead worrying about writing prototypes we are going to be writing sugar Classes in ES6.

> JS doesn't have classes, it does something that’s called prototypes JS will still have prototypes ES6 add syntactic sugar code on top of this.

[Ej1: Classes and Inheritance](http://www.es6fiddle.net/ibnhqzdy/)

---
## 05 Modules: 
Modules are stored in files. 
The goal for ECMAScript 6 modules is to create a format that both users of CommonJS and of AMD are happy with.

```javascript
//------ lib.js ------
export const sqrt = Math.sqrt;

export function square(x) {
    return x * x;
}
export function diag(x, y) {
    return sqrt(square(x) + square(y));
}

//------ main.js ------
import { square, diag } from ‘src/lib';
console.log( square(11) ); // 121
console.log( diag(4, 3) ); // 5
```
[Ej1: NotWorkingExample](http://www.es6fiddle.net/ibnjc164/)


06. 

07.

08.a

09.

10. Promises
The Promise object is used for deferred and asynchronous computations (the action of mathematical calculation). 

> A Promise represents an operation that hasn't completed yet, but is expected to in the future.

1. A Promise can have one of these states:
1.1 Pending: initial state, not fulfilled or rejected.
1.2 Fulfilled: meaning that the operation completed successfully: fulfilled with a value
1.3 Rejected: meaning that the operation failed: rejected with a reason (error).


> ES6 standardise promises and remove the external dependencies currently required to use promises.


``A pending promise can become either fulfilled with a value, or rejected with a reason (error).
As the Promise.prototype.then and Promise.prototype.catch methods return promises, they can be chained—an operation called composition.``

![alt text](https://mdn.mozillademos.org/files/8633/promises.png "EcmaScript6")
Source: developer.mozilla.org

### ES6 native Promise pattern
```javascript
// Promise Constructor
var promise = new Promise(function(resolve, reject) {
  if(true) {
    resolve("worked!");  
  } else {
    reject("didnt work");
  }

});

// ES6 promise instance
promise
  .then(function(result){
    console.log(result);
  }, function(error){
    console.log(error);
  });
```  
[Ej1: Native Promises](http://www.es6fiddle.net/ibth213t/)

11.

12.

13.


---
## 05. New utility methods for Strings, Arrays and additions to the Number and Object object
### String.prototype and Array.prototype

### Array.prototype.fill()
```javascript
console.log( ['a', 'b', 'c'].fill("") ); // Array [ "", "", "" ]
```
[Ej1: fill](http://www.es6fiddle.net/ibt922uk/)

###  Array.prototype.find()
```javascript
console.log( [1, 2, 3].find(x => x == 3) );
```
[Ej1: find](http://www.es6fiddle.net/ibt98kd2/)

### Array.prototype..findIndex()
```javascript
[6, 8, -5].findIndex(x => x < 0)
```
[Ej1: findIndex](http://www.es6fiddle.net/ibt9a6nh/)

### String.prototype.startsWith()
```javascript
var str = 'Hello World!';
console.log(str.startsWith('Hello')); // True
```
[Ej1: startsWith](http://www.es6fiddle.net/ibt9bihb/)

### String.prototype.endsWith()
```javascript
var str = 'Hello World!';
console.log(str.endsWith('Hello')); // False
```
[Ej1: endsWith](http://www.es6fiddle.net/ibt9dddr/)

### String.prototype.includes()
```javascript
var str = 'Hello World!';
console.log(str.includes(' ')); // True
console.log( 'JS '.repeat(3) ); // JS JS JS
```
[Ej1: includes](http://www.es6fiddle.net/ibt9ef15/)

### Array.of()
```javascript
var arr = new Array([1,2,3]); // ES4.1
var arr1 = [1, 2, 3]; // ES4.1
let arr2 = Array.of(1, 2, 3); // ES6

console.log(arr);
console.log(arr1);
console.log(arr2);
```
[Ej1: Array.of](http://www.es6fiddle.net/ibtg9a0r/)


### Additions to the Number Object: isNaN
```javascript
Number.isNaN(0 / 0);   // true
Number.isNaN(NaN);        // true
Number.isNaN(undefined);  // false
Number.isNaN({});         // false
```

### Additions to the Number Object: isFinite
```javascript
Number.isFinite(NaN);       // false
Number.isFinite(0);  
```

### Additions to the Object object: Object.is() 
> == and === both Operators are comparing same things, but == allows coercion and === disallows coercion, making === faster and more accurate.

Following best practices:
*Avoid == potential coerce errors 
*Use === operator and also make it faster or Object.is()
```javascript
console.log(1 == "1"); // true
console.log(1 === "1"); // false
Object.is(1,"1"); // false

console.log(NaN == NaN);
console.log(NaN === NaN); // false
Object.is(NaN,NaN); // true

console.log('' == 0);  // true
console.log('' === 0);  // false
console.log(Object.is('',0); // false
// doesn’t work on IE11
```

### Additions to the Object object: Object.assign()
For merging objects we will have the function 
```javascript
var obj = { a: 1 };
var copy = Object.assign({}, obj); // Object.assign(target, source_1, ..., source_n)
console.log(copy); // { a: 1 }

```

### Computed property keys
```javascript
let o1 = 'Jon';
let o2 = {[o1]: false,
          ['D'+'o'+'e']: null
};
console.log(JSON.stringify(o2));
```
[Ej1: Computed property keys](http://www.es6fiddle.net/ibnp05oa/)

### Default parameter values: =
```javascript
function f(x, y=12) { 
  // y is 12 if not passed (or passed as undefined) 
  return x + y; 
} 
console.log( f(3) == 15; )
```
[Ej1: Default parameter values](http://www.es6fiddle.net/ibtafirh/)


### Rest parameters values: ...
Replaces the need for using arguments to access functions arguments. It allows you to get to an array representing "The rest of parameters".

```javascript
```

### TODO from here -><-

### Spread parameters values


### spread operator:
```javascript
let arr = [-1, 7, 2, null, -0, +0, 10, 21];
let highest = Math.max(...arr);
console.log(arr); // 
console.log(highest);
```
[Ej1: spread operator](http://www.es6fiddle.net/ibt9lps8/)

### spread operator: (...) as parameters
```javascript
function restParameters(param, ...params) {
  return params;
}
console.log(restParameters('a', 'b', 'c')); // ['b', 'c']
```
[Ej1: spread operator as parameter](http://www.es6fiddle.net/ibnp05oa/)


### spread operator: (...) to turn strings into Arrays
```javascript
let chars = [...'Jon' + 'Doe'];
console.log(chars); // ["J", "o", "n", "D", "o", "e"]
```

### template literal
```javascript
let person = { name: 'Mr.' };
let name = 'Leo';
let tpl = `I'm: ${person.name} ${name}`; // we are using  with `back-ticks` or `grave-accent`
console.log(tpl);
```
[Ej1: template literal](http://www.es6fiddle.net/ibnoh9mz/)

### for...of
Strings are iterable, which means that you can use for-of to iterate over their characters
```javascript
for (let index of 'Jon Doe') {
    console.log(index);
}
```
[Ej1: for...of](http://www.es6fiddle.net/ibnq4vte/)
[Ej2: for...of with template literal](http://www.es6fiddle.net/ibnqk83n/)
[Ej3: for..of:loop throw Array]



### Symbol()
A new primitive type: Symbol()
They are tokens that serve as unique IDs.
This key avoid accidentally clash with any other property key:
```javascript
let symbol1 = Symbol();
let symbol2 = Symbol();

console.log(typeof symbol1);
console.log( Object.is(symbol1,symbol2) );

let wrap = Object(symbol2);
console.log(typeof wrap);
console.log(wrap instanceof Symbol)
console.log('symbol2 symbol: ' + String(symbol2) );
```
[Ej1: Symbol](http://www.es6fiddle.net/ibnsu6sd/)


### computed property keys
You can specify the key of a property via an expression, by putting it in square brackets. In the following object literal, we use a computed property key to make the value of MY_KEY the key of a property.
```javascript
const _id = Symbol(); // generate Unique token and cannot be changed
let obj = {
    [_id]() { // specify the key of a property via an expression
        return 'ID007';
    }
};
console.log( obj[_id]() ); // ID007
```
[Ej1: computed property keys](http://www.es6fiddle.net/ibnrh8ot/)

---
# 3-  Should I Use ES6 Now or Wait?. How to start using ES6 now?
![alt text](http://leolanese.com/es6-5.png "transpilers")



it’s possible to use ES6 today while still targeting older browsers. This is possible thanks to "transpilers" that can convert ES6 code to ES5, we can implement a transpiler into our development workflow and use ES6 that's goign to be automaticly transform into ES5 using Gulp or Grunt .

## Transpilers: using Babel
![alt text](http://svgporn.com/babel.svg "Babel")
[Babel Playgroud](https://babeljs.io/repl/) 

-[todo: incluir example]-

## Transpilers: using Google Traceur 
[Google Traceur Playgroud](https://google.github.io/traceur-compiler/demo/repl.html) 
-[todo: incluir example]-

## Automatic Transpilers: using Gulp, Babel, NodeJS: Using ES6

[gulp-es6-seed](https://github.com/sirwilliam/gulp-es6-seed)




---
# 4- My favourites ES6 Playgrounds and Resources:

![alt text](http://svgporn.com/github-icon.svg "Babel")

## ES6 Resources
Looking for   | Go to
------------- | -------------
ES6Features  | [ES6](https://github.com/lukehoban/es6features)
ECMAScript 6 compatibility Table | [Can I use ES6](http://kangax.github.io/compat-table/es6/)
Test My  browser     | [ES6 checker](http://ruanyf.github.io/es-checker/)
Harmony Specification | [ECMA-262 Edition-6](http://wiki.ecmascript.org/doku.php?id=harmony:specification_drafts)


## ES6 transpilers
Looking for   | Go to
------------- | -------------
Typescriptlang          |[http://www.typescriptlang.org/](http://www.typescriptlang.org/Playground)
BabelJS       |[babeljs.io](https://babeljs.io/repl/)
Traceur        |[google.github.io](http://google.github.io/traceur-compiler/demo/repl.html#)
ES6Fiddle          |[ES6Fiddle](http://www.es6fiddle.net/)

## ES6 Documentation
Looking for   | Go to
------------- | -------------
Exploring-es6  Book        | [Axel Rauschmayer](https://leanpub.com/exploring-es6/read)
UnderstandingES6  Book      | [Nicholas C. Zakas](https://leanpub.com/understandinges6/read)
ECMAScript 6 Tools | [Addy Osmani](https://github.com/addyosmani/es6-tools)


