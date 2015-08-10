# 3-  When can I start using ES6? 
![alt text](http://leolanese.com/es6-5.png "transpilers")

How to start using ES6 now?
```it's possible to use ES6 today while still targeting older browsers. This is possible thanks to "transpilers"``` that can convert ES6 code to ES5, we can implement a transpiler into our development workflow and use ES6 that's goign to be automaticly transform into ES5 using Gulp or Grunt .

## Transpilers: using Babel
![alt text](http://www.leolanese.com/babel.svg "babel")
[Babel Playgroud](https://babeljs.io/repl/) 

### Dynamically transpiled ES6 on Node.js via Babel

### Install Babel:
```
npm install --save-dev -g babel
```

### Test ES6 on Terminal:
```
babel-node
[1,2,3].map(x => x * x); // [ 1, 4, 9]
```

### That will transform into ES5:
```javascript
"use strict";

[1, 2, 3].map(function (x) {
  return x * x;
});
```
[ES6/ES5 Babel playground](https://babeljs.io/repl/#?experimental=true&evaluate=true&loose=true&spec=true&playground=true&code=%5B1%2C2%2C3%5D.map(x%20%3D%3E%20x%20*%20x)%3B)


### Another ES6 on terminal:
```
const sum = arr => arr.reduce((a, b) => a + b);
console.log( 'sum: ', sum([1,2,3]) )
```

### That will transform into ES5:
```javascript
'use strict';

var _temporalUndefined = {};
var sum = _temporalUndefined;

function _temporalAssertDefined(val, name, undef) { if (val === undef) { throw new ReferenceError(name + ' is not defined - temporal dead zone'); } return true; }

sum = function sum(arr) {
  return arr.reduce(function (a, b) {
    return a + b;
  });
};

console.log('sum: ', (_temporalAssertDefined(sum, 'sum', _temporalUndefined) && sum)([1, 2, 3]));
```
[ES6/ES5 Babel playground](https://babeljs.io/repl/#?experimental=true&evaluate=true&loose=true&spec=true&playground=true&code=const%20sum%20%3D%20arr%20%3D%3E%20arr.reduce((a%2C%20b)%20%3D%3E%20a%20%2B%20b)%3B%0Aconsole.log(%20'sum%3A%20'%2C%20sum(%5B1%2C2%2C3%5D)%20))

![alt text](http://leolanese.com/tc.png "Google Traceur")
## Google Traceur Transpilers: using Transpilers on the terminal
### Google traceur-compiler transpiler
```
git clone https://github.com/google/traceur-compiler.git
cd traceur-compiler
npm install
make
```

```
// go to:
cd example
open hello.html

// Now let edit the ES6 JS: 
example/hello.html
```

```
/traceur-compiler/
./traceur --version
nano test.js
```

```
class Greeter {
  sayHi(name = 'Anonymous') {
    console.log(`Hi ${name}!`);
  }
}
var greeter = new Greeter();
greeter.sayHi();
```

```
sudo ./traceur --out out/test.js --script test.js
```

### This generate: 
```
/out/test.js
```

### Using using Transpilers on the browser: We take the 'out/test.js' on the browser
```
// we are going to use the: 'out/test.js'
<html>
  <head>
    <script src="bin/traceur.js"></script>
    <script src="out/test.js"></script>
  </head>
  <body>
    Check your console…
  </body>
</html>
```

### Try it out in the browser
[Google Traceur Playgroud](https://google.github.io/traceur-compiler/demo/repl.html) 

---

![alt text](http://www.leolanese.com/gulp.svg "gulp")
![alt text](http://www.leolanese.com/grunt.svg "grunt")
# Automatic Transpilers: Building Automatically using Gulp, Babel, NodeJS: Using ES6
### Small demo project demonstrates how to use the ES6 transpiler Babel on Node.js
[gulp-es6-seed](https://github.com/sirwilliam/gulp-es6-seed)

### Install Node dependencies
```
npm install
```
### run transpiled on terminal:
```
babel-node point.js // My point: {"x":7,"y":4}
```
