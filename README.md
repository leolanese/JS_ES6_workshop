# ES6 workshop
## The road to ECMAScript 6: New solutions for old JS problems.

![alt text](https://farm8.staticflickr.com/7306/16407404782_8b9c57eab3_m.jpg "EcmaScript6")

ECMA Script 6 is already here, and more and more of the production libraries and frameworks we use to create our applications are going to be written using this new version of JavaScript. Instead of waiting on the sidelines, we can start using ES6 now with the help of transpilers/shim, and enjoy many of the benefits without worrying about browser compatibility.

## Goal of the Workshop:
1. Introduction to new ES6 features.
2. How to use these features today.


Further information:
Looking for   | Go to
------------- | -------------
Typescriptlang          | [View](https://www.google.com) 
Typescriptlang          | [GITHUB](https://github.com/sirwilliam/ES6_workshop.git) 
Typescriptlang          |[LeoLanese Twitter](https://twitter.com/leolaneseltd) 

----
Topics:

1. What is ES6? 
2. Key Features in ES6
3. Should I Use ES6 Now or Wait?. How to start using ES6 now?
4. 'Hello ES6 World'?
5. What next?

----
# 1- What is ES6?: 

## Goal: Be a better language

### "ES6 will change the way you write JS code."
To tell you the true, when I read this quote it’s scared me a little bit, thinking old code old knowledge could go to the bin.
Reality check: **ES6 is an enhancement of ES5.** ES6 brings new features, solve few problems and it can be partially or complete incorporated to our code and make things easy to understand.

### Why we want to learn ES6?
We are developers, we are progressive. **We want to learn the latest things so we can build the best applications possible.**
We will be ready, our product will be future proof and as a developer we will be more marketable as a coder in the industry, this will positioning an step ahead and we will be ready for AngularJS 2.

### AngularJS 2:
**AngularJS2 it’s going to be a big deal.**
If you worry to get ready to AngularJS2, about being ready from a knowledge standpoint there are some new things that you should know about.

### What can we do right now in order to be up to date when AngularJS 2 comes?
If you want to be ready for AJS2 we can start learning ES6, and **we’ll be ahead of the game**.
We can be ready and prepared focusing on one thing in particular: ES6

### Do I need to migrate my javaScript code to ECMAScript 6?
**There is no need**: ECMAScript 6 is a superset of ECMAScript 5. Therefore, all of your ES5 code is automatically ES6 code. How exactly ES6 stays completely backwards compatible

---
# 1- Key Features in ES6:

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
Up to ES6 variables are always function scoped: So, no matter where you declare your variable, these are going to be hoisted on the top of the scope.

Variable declared using let will only be available in the ‘current block’ instead of the ‘entire function’ when using var.
The let keyword allows you to define variables within the scope of the block (block scoping).

>  Don't replace let for var

### EJ:
#### let w/function:
[let w/function](http://www.es6fiddle.net/ibt75xzh/)

#### let w/looping:
[let w/looping](http://www.es6fiddle.net/ibt7tkvh/)


### const()
We will be able to create constants and make sure its value won’t be changed
[Example](http://www.es6fiddle.net/ibs2z9yg/)


---
## 02. Arrow functions: =>
Providing a work around to: ‘that = this’ or ‘bind()’
With a more compact version of an ‘anonymous function syntax’.

Ej1
[Example](http://www.es6fiddle.net/ibs23tom/)

Ej2: ES5 Vs. ES6
[ES5](http://jsfiddle.net/leolanese/uz9x15x7/)
[ES6](http://www.es6fiddle.net/ibt3woe1/)


---
## 03. Block-level scope: {}
### This creates a Temporal Dead Zone

---
## 4- Classes and inheritance: class, extends, 
JS doesn't have classes, it does something that’s called prototypes
and while JS will still have prototypes, they’re going to add a little piece of what’s called syntactic sugar, or in other words, a simpler way of writing something on a different way.

>  Instead worrying about writing prototypes we are going to be writing sugar Classes in ES6.

Ej1:
[Classes and Inheritance](http://www.es6fiddle.net/ibnhqzdy/)


---
## 05 Modules: 
Modules are stored in files. 
The goal for ECMAScript 6 modules was to create a format that both users of CommonJS and of AMD are happy with. We can do similar things that using AMD CommnJS:

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

[NotWorkingExample](http://www.es6fiddle.net/ibnjc164/)

---
## 05. New utility methods for Strings and Arrays
###

### .fill()
```javascript
console.log(
	['a', 'b', 'c'].fill("")
);
```
[fill](http://www.es6fiddle.net/ibt922uk/)

###  .find()
```javascript
console.log( [1, 2, 3].find(x => x == 3) );
```
[find](http://www.es6fiddle.net/ibt98kd2/)

### .findIndex()
```javascript
[6, 8, -5].findIndex(x => x < 0)
```
[findIndex](http://www.es6fiddle.net/ibt9a6nh/)

### .startsWith()
```javascript
var str = 'Hello World!';
console.log(str.startsWith('Hello')); // True
```
[startsWith](http://www.es6fiddle.net/ibt9bihb/)

### .endsWith()
```javascript
var str = 'Hello World!';
console.log(str.endsWith('Hello')); // False
```
[endsWith](http://www.es6fiddle.net/ibt9dddr/)

### .includes()
```javascript
var str = 'Hello World!';
console.log(str.includes(' ')); // True
console.log( 'JS '.repeat(3) ); // JS JS JS
```
[includes](http://www.es6fiddle.net/ibt9ef15/)

### Computed property keys
```javascript
let o1 = 'Jon';
let o2 = {[o1]: false,
          ['D'+'o'+'e']: null
};
console.log(JSON.stringify(o2));
```
[Computed property keys](http://www.es6fiddle.net/ibnp05oa/)

### Default parameter values: =
```javascript
function f(x, y=12) { 
  // y is 12 if not passed (or passed as undefined) 
  return x + y; 
} 
console.log( f(3) == 15; )
```
[Default parameter values](http://www.es6fiddle.net/ibtafirh/)


### Rest parameters values: ...
Rest replaces the need for arguments
```javascript
```
### TODO from here

### Spread parameters values


### spread operator:
```javascript
let arr = [-1, 7, 2, null, -0, +0, 10, 21];
let highest = Math.max(...arr);
console.log(arr); // 
console.log(highest);
```
[spread operator](http://www.es6fiddle.net/ibt9lps8/)

### spread operator: (...) as parameters
```javascript
function restParameters(param, ...params) {
  return params;
}
console.log(restParameters('a', 'b', 'c')); // ['b', 'c']
```
[spread operator as parameter](http://www.es6fiddle.net/ibnp05oa/)


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
[template literal](http://www.es6fiddle.net/ibnoh9mz/)

### for...of
Strings are iterable, which means that you can use for-of to iterate over their characters
```javascript
for (let index of 'Jon Doe') {
    console.log(index);
}
```
[ej1-for...of](http://www.es6fiddle.net/ibnq4vte/)
[ej2-for...of with template literal](http://www.es6fiddle.net/ibnqk83n/)
[ej3-for..of:loop throw Array]



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
[Symbol](http://www.es6fiddle.net/ibnsu6sd/)


----

# 5- My favourites ES6 playgrounds and Resources:

## ES6 Features
Looking for   | Go to
------------- | -------------
ES6Features  | [ES6](https://github.com/lukehoban/es6features)
ECMAScript 6 compatibility Table | [Can I use ES6](http://kangax.github.io/compat-table/es6/)
Test My  browser     | [ES6 checker](http://ruanyf.github.io/es-checker/)


## Further information:
Looking for   | Go to
------------- | -------------
Typescriptlang          |[http://www.typescriptlang.org/](http://www.typescriptlang.org/Playground)
BabelJS       |[babeljs.io](https://babeljs.io/repl/)
Traceur        |[google.github.io](http://google.github.io/traceur-compiler/demo/repl.html#)
ES6Fiddle          |[ES6Fiddle](http://www.es6fiddle.net/)

## RESOURCES:
Looking for   | Go to
------------- | -------------
exploring-es6          | [Axel Rauschmayer - Book](https://leanpub.com/exploring-es6/read)
UnderstandingES6        | [Nicholas C. Zakas - Book](https://leanpub.com/understandinges6/read)

