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

## Indention
Use 4 spaces with soft TAB.

## Newline
Use UNIX-style newlines (`\n`), and a newline character as the last character of a file. Windows-style newlines (`\r\n`) are forbidden inside any repository.

## Trailing whitespace
Clean up any trailing whitespace in javascript files.

## Semicolon
Leave semicolons is dangerous because it can make mask errors, so use them.

## Line break
Limit your lines to 80 characters. Screens have gotten much bigger, but your brain has not.

## Line number
Keep max 40 lines per file. Easier to understand if you see everything in a file without scrolling.

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










