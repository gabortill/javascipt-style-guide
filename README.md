# JavaScript Style Guide
This is my guide for writing consistent JavaScript code.



## Table of contents
* [Indention](#indention)
* [Newline](#newline)
* [Trailing whitespace](#trailing-whitespace)
* [Semicolon](#semicolon)
* [Line break](#line-break)
* [Line number](#line-number)
* [Quotation mark](#quotation-mark)
* [Curly brace in decision block](#curly-brace-in-decision-block)
* [Chaining](#chaining)
* [Variable declaration](#variable-declaration)
* [Naming](#naming)
* [Array](#array)
* [Object](#object)
* [Equality](#equality)
* [Built-in](#built-in)
* [Comment](#comment)



## Indention
Use 4 spaces with soft TAB.

**why?**

4 spaces are imporve readabillity and the use of spaces can produce a larger filesize.



## Newline
Use UNIX-style newlines (`\n`), and a newline character as the last character of a file.

**why?**

Windows-style newlines (`\r\n`) are forbidden inside any repository.



## Trailing whitespace
Clean up any trailing whitespace in javascript files.

**why?**

Trailing whitespaces are unnecessary and improve the filesize.



## Semicolon
Always use semicolons.

**why?**

Leave semicolons is dangerous because it can make mask errors.



## Line break
Limit your lines to 100 characters. Place the break after an operator, ideally after a comma. The next line should be indented more 4 spaces.

**why?**

Screens have gotten much bigger, but your brain has not. A break after an operator decreases the likelihood that a copy-paste error will be masked by semicolon insertion.



## Line number
Keep max 40 lines per file.

**why?**

Easier to understand if you see everything in a file without scrolling.



## Quotation mark
Use single quotes. This is helpful when creating strings that include HTML.
```js
// BAD
var bad = "BAD";
var elem = "<input type=\"text\" />";
```
```js
// GOOD
var good = 'GOOD';
var elem = '<input type="text" />';
```



## Curly brace in decision block
Always use curly braces with multiline blocks (opening braces go on the same line as the statement).
```js
// BAD
if (true) console.log('BAD');
```
```js
// BAD
if (true)
{
    console.log('BAD');
}
```
```js
// GOOD
if (true) {
    console.log('GOOD');
}
```



## Chaining
Use one method per line if you want to chain methods. Also indent these methods, because it's easier to tell they are part of the same chain.
```js
// BAD
var bad = new Bad();

bad
.methodOne()
.methodTwo()
.methodThree();
```
```js
// BAD
var bad = new Bad();

bad.methodOne()
    .methodTwo()
    .methodThree();
```
```js
// GOOD
var good = new Good();

good
    .methodOne()
    .methodTwo()
    .methodThree();
```



## Variable declaration
The var statement should be the first statement in the function body. Avoid single var pattern and declare every variable before used. These are makes the program easier to read.
```js
// BAD
var badString = 'I am BAD',
    badElem = document.getElementById('bad-elem'),
    badArr = ['one', 'two', 'three'],
    badObj = {
      'one': 1,
      'two': 2,
      'three': 3
    };
```
```js
// GOOD
var goodString = 'I am GOOD';
var goodElem = document.getElementById('good-elem');
var goodArr = ['one', 'two', 'three'];
var goodObj = {
  'one': 1,
  'two': 2,
  'three': 3
};
```



## Naming
Use descriptive lowerCamelCase naming for variables, properties and functions except constructor functions. Constructor functions that must be used with the new prefix and UpperCamelCase naming. Do not use reserved words.
```js
// BAD
var badname = 'I am BAD';
```
```js
// BAD
var bad_name = 'underbar is BAD';
```
```js
// BAD
var BADNAME = 'There is no constants in ECMAScript 5';
```
```js
// BAD
var a = 'avoid single character names';
```
```js
// GOOD
var goodName = 'I am GOOD';
```



## Array
Use Array literals instead of constructors. [Array constructors are error-prone due to their arguments.](https://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml?showone=Array_and_Object_literals#Array_and_Object_literals)
```js
// BAD
var badArr = new Array();
```
```js
// GOOD
var goodArr = [];
```

Single line Array initializer – no space after [ and before ].
```js
// BAD
var badArr = [ 'one', 'two', 'three' ];
```
```js
// GOOD
var goodArr = ['one', 'two', 'three'];
```
```js
// multiline array initializer is BETTER
var goodArr = [
    'one',
    'two',
    'three'
];
```

Never use Array as a map/hash/associative array.
```js
// BAD
var skills = [];
skills['Document language'] = 'HTML5';
```
```js
var skills = {
    'Document language': 'HTML5'
};
```



## Object
Use literal syntax for object creation. They don't have the constructor problem like Arrays, but be consistent.
```js
// BAD
var badObj = new Object();
```
```js
// GOOD
var goodObj = {};
```

Single line Object initializer – no space after { and before }.
```js
// BAD
var badObj = { a: 0, b: 1, c: 2 };
```
```js
// GOOD
var goodObj = {a: 0, b: 1, c: 2};
```
```js
// multiline object initializer is BETTER
var goodObj = {
    a: 0,
    b: 1,
    c: 2
};
```

Do not align to the colon.
```js
// BAD
var badObj = {
    bottom : 15,
    left   : 15,
    right  : 20,
    top    : 110
};
```
```js
// GOOD
var goodObj = {
    bottom: 15,
    left: 15,
    right: 20,
    top: 110
};
```


## Equality
The == and != operators do type coercion before comparing therefore use === and !== operators.



## Built-in
Never extend the prototype of native JavaScript objects unless polyfilling.
```js
// BAD
Array.prototype.empty = function () {
    return !this.length;
};

var badArr = [];
if (badArr.empty()) {
    console.log('I am BAD');
}
```
```js
// GOOD
var goodArr = [];

if (!goodArr.length) {
    console.log('I am GOOD');
}
```



## Comment
Generally use single line comments. Place single line comments on a newline of subject and put an empty line before.

**why?**

Save block comments for formal documentation. Empty lines above comments are improve readabillity.

```js
// BAD
var bad = true; // comment in wrong place
```
```js
// BAD
var bad;
// missing empty newline
bad = true;
```
```js
// BAD
/*
block comments
for documentation
*/
var bad = true;
```
```js
// GOOD
var good;

// set to true
good = true;
```





























