# 2- Key Features in ES6:

![alt text](http://www.leolanese.com/es6.svg "JS")

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

=======================================================================================================================
-- 01. Block Scope: let and const
### let()
Up to ES6 variables are always function scoped: So, ``no matter where you declare your variable, these are going to be hoisted on the top of the scope.``

>  Don't replace let for var

### Difference bettween 'var' and 'let':
The difference is **scope** (the location where variables lives): 
The variables declared with 'var' are scoped to the function block (or global if outside a function block) while those declared with 'let' are scoped to the enclosing block (or global if outside any block) which may be smaller than the function block.

> In other words: Variable declared using 'let' will only be available in the 'current block', using var will be on the 'entire function'. The let keyword allows you to define variables within the scope of the block (block scoping).

### Eg. Difference between 'var' and 'let':
On es5var : The variable i, declared with var keyword, is hoisted and is available to the whole function.
On es6let: The variable i is scoped to the for loop. It's visible just inside the parentheses and the curly braces of the loop.
```javascript
function es5var(){
    // i is visible here due to variable hoisting
   for(var i=0; i<10; i++){
      console.log(i);
      // of course i is available here 
   }
   // i is available as well 
   console.log(i);
}
es5var();


// ES6 using let
function es6let(){
    // i is NOT visible here
   for(let i=0; i<10; i++){
      console.log(i);
      // i IS BLOCK SCOPE to this block {}
   }
   // i is NOT available here
   // console.log(i);
}
es6let();
```
[Eg. difference ES5 'var' and ES6 'let'](http://www.es6fiddle.net/icoyi4u4/)


### Creating Objects:
```javascript
// ES5
var o1 = "test";
var o2 = "test2";
var o3 = { o1:o1, o2:o2 };
console.log( o3 ); // Object {o1: "test1", o2: "test2"}
```
[eg1:](http://www.es6fiddle.net/icg82t9k/)

```javascript
// ES6
let o1 = "test1";
let o2 = "test2";
let o3 = { o1,o2 };
console.log( o3 ); // Object {o1: "test1", o2: "test2"}
```
[eg1:](http://www.es6fiddle.net/icg84b9e/)

## Create var from Arrays:
```javascript
// ES5
var c = [1,2,3];
var p = c[0];
console.log(p);
```
```javascript
// ES6
var c = [1,2,3];
var [a1,a2,a3] = c;
console.log(1,2,3)

## Creating Arrays:
```javascript
// ES6
Array.of(1, 2, 3); 

```

#### let w/function with scope and block scope:
```javascript
// scope
function fScope() {
    if(true) {
        var sun = 'here'; // sun is "hoisted" to the function block
    }
    console.log('sun is ' + sun); // sun is visible
}
fScope();


// block scope
// the let keyword allows you to define variables within the scope
function fBlockScoped() {
    if(true) {
        let sun = 'here'; // sun is NOT "hoisted" out of this block
    }
    console.log('sun is ' + sun); // sun is not defined
}
fBlockScoped();
```
[Ej1: let w/function](http://www.es6fiddle.net/ibt75xzh/)

#### let w/looping:
```javascript
// error on j2
for(var v = 0; v < 10; v++) {
    // 'v' is only available within the for block
   console.log(v);
   //var v2 = v;
}

for(let j = 0; j < 10; j++) {
    // 'j' is only available within the for block
   console.log(j);
   let j2 = j;
}
console.log("var -->", v); 
console.log("let -->", j); // error j is not defined because of let
```
[Ej2: let w/looping](http://www.es6fiddle.net/ibwh8qpk/)

```javascript
for (let l = 0; l < 3; l++) {
console.log('loop:', l);
}
console.log('after loop:', typeof l);

for (var v = 0; v < 3; v++) {
console.log('loop:', v);
}
console.log('after loop:', typeof v);
```
[Ej3: let w/looping](http://www.es6fiddle.net/ibwh5v5x/)


### const()
We will be able to create constants and make sure its value won’t be changed
```javascript
const no = [{'here':'there'}, {'owesome':'ES6'}];
console.log(no);

// var no = [{'no':'posible'}];
console.log(no);
```
[Ej1: const](http://www.es6fiddle.net/ibs2z9yg/)

=======================================================================================================================
-- 02. Arrow functions: => [ecma-international.org](http://www.ecma-international.org/ecma-262/6.0/#sec-arrow-function-definitions)
```javascript
// ES5
var sayHello = function(msn, name){
    return msn + ' ' + name;
};
console.log(sayHello('Hi','there'));

// ES6
let sayHello = (msn, name) => {
    return msn + ' ' + name;
};
console.log(sayHello('Hi','there'));
```
[Ej1: Arrow](http://www.es6fiddle.net/ic2fdnx2/)

```javascript
// ES6
var sayHello = (msn, n) => msn + ' ' + n;
console.log(sayHello('Hi','there'));
```
[Ej1 - short](http://www.es6fiddle.net/ic2g5hxj/)


> Provide a work around to: ‘that = this’ or ‘bind()’, with a more compact version of an ‘anonymous function syntax’.

```javascript
setTimeout(() => { console.log('Hello'); }, 2000);  
```
[Ej2: Example](http://www.es6fiddle.net/ibw4crgq/)
```javascript
let square = num => num * num;
console.log( square(10) );
```
[Ej3: Example](http://www.es6fiddle.net/ibtfr5fk/)


=======================================================================================================================
-- 3- Block-level scope: {} [ecma-international.org](http://www.ecma-international.org/ecma-262/6.0/#sec-block-level-function-declarations-web-legacy-compatibility-semantics)
### This creates a Temporal Dead Zone



=======================================================================================================================
-- 4- Classes and inheritance: class, extends, setters, getters, super, etc [ecma-international.org](http://www.ecma-international.org/ecma-262/6.0/#sec-ecmascript-language-functions-and-classes)
ES6 Classes are simplre sugar over the prototype-based OO Pattern. 

> Instead worrying about writing prototypes we are going to be writing sugar Classes in ES6.

### classes, constructor, getters, and setters
```javascript
class Foo {
  constructor(p1, p2) {
    this.p1 = p1;
    this.p2 = p2;
  }

  get name() {
    return this.p1 + " " + this.p2;
  }

  set name(name) {
    var names = name.split(" ");

    this.p1 = names[0];
    this.p2 = names[1];
  }
}

var hello = new Foo("Hello", "World!");
hello.world = "Hello World!";
console.log(hello.world);
```
[Ej1: ES6 Classes and Contructor](http://www.es6fiddle.net/ibyylfm7/)

> JS doesn't have classes, it does something that’s called prototypes JS will still have prototypes ES6 add syntactic sugar code on top of this.

### extends
```javascript
class Car {
    constructor(x, y) {
        this.x = x;
        this.y = y;
    }
    toString() {
        return '(${this.x}, ${this.y})';
    }
    static classMethod() {
        return 'test';
    }
}

// Point: Car class and Fiat: subclass
class Fiat extends Car {
    constructor(x, y, color) {
        super(x, y);
        this.color = color;
    }
    toString() {
        return super.toString() + ' in ' + this.color;
    }
}

console.log(typeof Car); // function :)
let cp = new Fiat(10, 5, 'red'); // we can only invoke a class via new
console.warn(cp); // function Fiat {x: 25, y: 8, color: "red"}
console.log(cp instanceof Fiat); // true
console.log(cp instanceof Car); // true

// The prototype of a subclass is the superclass
console.log( Object.getPrototypeOf( Car) ); // Car
console.log( Object.getPrototypeOf( Fiat ).toString() ); //  means thats methods and properties are inherited function Car(x, y) {…}

console.log( Fiat.classMethod() );
```
[Ej2: ES6 Inheritance](http://www.es6fiddle.net/ibnhqzdy/)

## Classes
```javascript
function Car() {
    
  var that = this; //locally assign this that can be closed over
    
  that.speed = 0;

  setInterval(function goFaster() {
    //this has a different scope, but we can use the self variable to reference the parent "this"
    that.speed += 5;
      console.log('now going: ' + that.speed);
  }, 2000);
    
}

var car = new Car();
console.warn(car)
```
[Ej3: ES5 Vs. ES6: ES5 version](http://jsfiddle.net/leolanese/uz9x15x7/)
Vs.
```javascript
function Car() { //Note, we could use the new Class feature in ES6 instead

  this.speed = 0;

  setInterval(() => {
    this.speed += 5; //this is from Car
    console.log('now going: ' + this.speed);
  }, 1000);

}

let car = new Car();
console.log(car)
```
[Ej3: ES5 Vs. ES6: ES6 version](http://www.es6fiddle.net/ibtfwm70/)


=======================================================================================================================
-- 05 Modules [ecma-international.org](http://www.ecma-international.org/ecma-262/6.0/#sec-ecmascript-language-scripts-and-modules)
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

=======================================================================================================================
-- 06. New utility methods for Strings, Arrays and additions to the Number and Object object
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
[Ej1: endsWith()](http://www.es6fiddle.net/ibt9dddr/)

### String.prototype.includes()
```javascript
var str = 'Hello World!';
console.log(str.includes(' ')); // True
console.log( 'JS '.repeat(3) ); // JS JS JS
```
[Ej1: includes()](http://www.es6fiddle.net/ibt9ef15/)

### Array.of(element0[, element1[, ...[, elementN]]])
```javascript
var arr = new Array([1,2,3]); // ES4.1
var arr1 = [1, 2, 3]; // ES4.1
let arr2 = Array.of(1, 2, 3); // ES6

console.log(arr); // 1,2,3
console.log(arr1); // 1,2,3
console.log(arr2); // 1,2,3 
```
[Ej1: Array.of](http://www.es6fiddle.net/ibtg9a0r/)


### Array.from(arrayLike[, mapFn[, thisArg]])
```javascript
function a(){
  return Array.from(arguments);
}
console.log( a(1, 2, 3));  // [1, 2, 3]
```
[eg: Array.from](http://www.es6fiddle.net/icg8ah1y/)

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
We can now set defaults when defining arguments
```javascript
function f(x, y=10, z=20) { 
  // y is 10 and z is 20 if not passed (or passed as undefined) 
  console.log(x , y , z); // 3 10 20
  console.log(x + y + z); // 33
  return x + y + z; 
} 
console.log( f(3) == 33 )
```
[Ej1: Default parameter values](http://www.es6fiddle.net/ibw4x9n8/)


### Rest parameters values: ...
Replaces the need for using arguments to access functions arguments. It allows you to get to an array representing "The rest of parameters".

```javascript
function multiply(multiplier, ...theArgs) {  
  console.log(multiplier + ' - '+ theArgs); // 2 - 1,2,3  
  
  return theArgs.map(function (element) {
    console.log(element); // 1,2,3  
    return multiplier * element;
  });
  
}

var arr = multiply(2, 1, 2, 3);  
console.log(arr); // [2, 4, 6]  
```
[Ej1: Rest using map](http://www.es6fiddle.net/ibwgv30g/)

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

### for-of loops [ecma-international.org docs](http://www.ecma-international.org/ecma-262/6.0/#sec-for-in-and-for-of-statements)
In addition to the classic for-in statement, ES6 has added the for-of statement .

**Strings are iterable, which means that you can use for-of to iterate over their characters
While for-in iterates over "property names", for-of iterates over "property values"**

### basic syntax for-in
```javascript
for (let index in 'Jon Doe') { // property names
    console.log(index); // 0,1,2,3,4,5,6
}
```
[Eg: for-in](http://www.es6fiddle.net/icg5tsxn/)

```javascript
for (let index of 'Jon Doe') { // property values
    console.log(index); // J,o,n,,D,o,e
}
```
[Eg: for-in](http://www.es6fiddle.net/icg5u5q0/)


```javascript
var arr = [1, 2, 3];
for (var n of arr) console.log(n); // 1,2,3
```
[Eg3: simple for-of loop throw Array](http://www.es6fiddle.net/icg95lvv/)

```javascript
for (let index of 'Jon Doe') {
    console.log(index);
}
```
[Eg1: for-of](http://www.es6fiddle.net/ibnq4vte/)


```javascript
let arr = ['Hello', 'world', "!"];

for (let element of arr) {
  console.log(element);
}

for (let [index,element] of arr.entries()) {
  console.log(`${index}. ${element}`);
}
```
[Eg2: for-of with template literal](http://www.es6fiddle.net/ibnqk83n/)





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

=======================================================================================================================
-- 07. Destructuring [ecma-international.org](http://www.ecma-international.org/ecma-262/6.0/#sec-destructuring-binding-patterns)
Extract data from arrays or objects using a syntax that mirrors the construction of array and object literals


=======================================================================================================================
-- 08. Generators: yield(pause), next()(resume), function*/ function * [ecma-international.org/](http://www.ecma-international.org/ecma-262/6.0/#sec-generator-abstract-operations)
With ES6 generators creates a function, which may be paused and resume execution, one or many times, allowing other code to run during these paused periods.

> ES6 generator functions are "cooperative" in their concurrency behavior. 

This  ideal for creating functions that should be exited and continued later: we run the generator and yield when we restart the generator again, we will send a value back in, and whatever we send in will be the computed result of that yield ___ expression.

> Generator objects are both iterator and iterable.

> Provides a solutions for a endless callback problem

What is a Generator?
- it is now possible to suspend code execution
- Factory for special type of function declared using function* or function *
- Can be exited at any point using: yield
- Resumes at same point and same state if invoked back again
- Provides 2-way communication: 
We trigger the generator, the yield value it sends out, generator is paused, later (at any time), generator is trigger again thnen is restarted and will give a value back.


```javascript
// both are valids
function* foo(){ }

function *foo(){ }
```

```javascript
function *foo() {
    yield 1;
    return 2;
}

var it = foo();

console.log( it.next() ); // { value:1, done:false }
console.log( it.next().value ); // undefined
console.log( it.next() ); // { value:2, done:true }
console.log( it.next() ); // { value:undefined, done:true }
console.log( it.next().value ); // undefined
console.log( it.next().done ); // true
```
[Eg1: ES6 generators: value, done](http://www.es6fiddle.net/icgaoklw/)


```javascript
function* counter(){
  var index = 0;
  while(true) yield index++;
}
var c = counter();

console.log( c.next() ); // Object {value: 0, done: false}
console.log( c.next().value ); // 1
console.log( c.next().done ); // false
```
[eg2: ES6 generators: value, done](http://www.es6fiddle.net/icgaluf9/)


```javascript
function *foo(x) {
    var y = 2 * (yield (x + 1));
    var z = yield (y / 3);
    return (x + y + z);
}

var it = foo( 5 );

// note: not sending anything into <code>next()</code> here
console.log( it.next() );       // { value:6, done:false }
console.log( it.next( 12 ) );   // { value:8, done:false }
console.log( it.next( 13 ) );   // { value:42, done:true }
```
[Eg2: ES6 generators: send](http://www.es6fiddle.net/ic3t2ex1/)


### Some frameworks already using Generators:
[CO Framework](https://github.com/tj/co)
[KAO Framework](http://koajs.com/#)

### More about them: 
[what-are-generators (tobyho.com)](http://tobyho.com/2013/06/16/what-are-generators/)
[es6-generators (davidwalsh)](http://davidwalsh.name/es6-generators)

=======================================================================================================================
-- 09. Map and WeakMap: set, get, delete [ecma-international.org](http://www.ecma-international.org/ecma-262/6.0/#sec-map-iterable)

```javascript
var m = new Map();

m.set("n", "nn");
console.log( m.size ); // 1

m.set("n1", "nn1");
console.log( m.size ); // 2

console.log( m.get("n") ); // nn
console.log( m.has("n1") ); // true
console.log( m.delete("n1") ); // true
console.log( m.has("n1") ); // false

m.forEach(function(value, key){ console.log( key + ' maps to ' + value) }) // n maps to nn
```
[Ej1: Map](http://www.es6fiddle.net/icg8kb43/)

### WeakMap
- Similar to Map
- The word "weak" refers to weak references. A weak reference is an object reference that is ignored by the garbage collector.
- Keys must be objetcs
- keys are garbage-collected (usefull to prevent memory leaks)
- Can't be iterated
- Cannot get the size of a WeakMap 
- Cannot iterate over it's keys or values
- WeakSet has no size property, or a way of iterating its members (references are weak so can be destroyes without notice)



=======================================================================================================================
-- 10. Promises [ecma-international.org](http://www.ecma-international.org/ecma-262/6.0/#sec-promise-executor)

ES6 standardise promises and remove the external dependencies currently required to use promises.

> [Promises and "Pyramid of Doom"](https://github.com/kriskowal/q)

1. A Promise can have one of these states:
1.1 Pending: initial state, not fulfilled or rejected.
1.2 Fulfilled: meaning that the operation completed successfully: fulfilled with a value
1.3 Rejected: meaning that the operation failed: rejected with a reason (error).

> A Promise represents an operation that hasn't completed yet, but is expected to in the future.

``A pending promise can become either fulfilled with a value, or rejected with a reason (error).
As the Promise.prototype.then and Promise.prototype.catch methods return promises, they can be chained—an operation called composition.``

![alt text](https://mdn.mozillademos.org/files/8633/promises.png "EcmaScript6")
Source: developer.mozilla.org

``
New ES6 promises are created through the Promise constructor. This constructor accepts a single argument, which is a function (called the executor) containing the code to execute when the promise is added to the job queue. The executor is passed two functions as arguments, resolve() and reject(). 
``
``
The resolve() function is called when the executor has finished successfully in order to signal that the promise is ready to be resolved while the reject() function indicates that the executor has failed.
``

### ES6 native Promise pattern
```javascript
// Defining: ES6 Promise Constructor
var promise = new Promise(function(resolve, reject) { // executor function with: resolve and reject function arguments
  if(true) {
    resolve("worked!");  
  } else {
    reject("didnt work");
  }
});

// Using: ES6 promise instance
promise
  .then(function(result){
    console.log(result);
  }, function(error){
    console.log(error);
  });
```  
[Ej1: Native Promises](http://www.es6fiddle.net/ibth213t/)

### ES6 Promises 
```javascript
// Defining Mock Data Service
var data;
function findData(){
  return new Promise(function (resolve, reject){
    if (data){
      resolve(data);
    }else{
      reject("data not found");
    }
  });
}

// Using Mock Data Service
promise
  .then(function(data){
    console.log(data);
  })
  catch(function(){
    console.log(error);
  })
```

### ES6 Chaining Promises: Returning Values in Promise Chains
```javascript
let foo = new Promise(function(resolve, reject) {
    return resolve(1);
});

foo.then(function(value) {		// value = 1 from executor 	
    console.log(value);         // "1"
    return value + 1;			// fulfillment handler returns 2	
}).then(function(value) {
    console.log(value);         // "2"
    return value + 1;			// fulfillment handler returns 3
}).then(function(value) {
    console.log(value);         // "3"
});
```
[Eg: Chaining Promises](http://www.es6fiddle.net/icn5doba/)

=======================================================================================================================
-- 11. Rest parameters      

=======================================================================================================================
-- 12. Set

=======================================================================================================================
-- 13. Template Strings

----------------------------------------------------------------------------------------------------------------------