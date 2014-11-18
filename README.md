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
1. Use 4 spaces.
2. Use soft TAB.

**why?**

1. 4 spaces are imporve readabillity.
2. Use of spaces can produce a smaller filesize.

**[⬆ back to top](#table-of-contents)**



## Newline
Use UNIX-style newlines (`\n`), and a newline character as the last character of a file.

**why?**

Windows-style newlines (`\r\n`) are forbidden inside any repository.

**[⬆ back to top](#table-of-contents)**



## Trailing whitespace
Clean up any trailing whitespace in javascript files.

**why?**

Trailing whitespaces are unnecessary and improve the filesize.

**[⬆ back to top](#table-of-contents)**



## Semicolon
Always use semicolons.

**why?**

Leave semicolons is dangerous because it can make mask errors.

**[⬆ back to top](#table-of-contents)**



## Line break
1. Limit your lines to 100 characters.
2. Place the break after an operator, ideally after a comma. The next line should be indented more 4 spaces.

**why?**

1. Screens have gotten much bigger, but your brain has not.
2. A break after an operator decreases the likelihood that a copy-paste error will be masked by semicolon insertion.

**[⬆ back to top](#table-of-contents)**



## Line number
Keep max 40 lines per file.

**why?**

Easier to understand if you see everything without scrolling.

**[⬆ back to top](#table-of-contents)**



## Quotation mark
Use single quotes.

**why?**

This is helpful when creating strings that include HTML.

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

**[⬆ back to top](#table-of-contents)**



## Curly brace in decision block
Always use curly braces with multiline blocks (opening braces go on the same line as the statement).

**why?**

To omit braces is decrease readabillity.

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

**[⬆ back to top](#table-of-contents)**



## Chaining
Use one method per line if you want to chain methods, and also indent these.

**why?$$

Because it's easier to tell they are part of the same chain.

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

**[⬆ back to top](#table-of-contents)**



## Variable declaration
1. All variables should be declared before used.
2. Avoid single var pattern and the var statements should be the first statement in the function body.

**why?**

1. Use of global variables should be minimized.
2. These are makes the program easier to read.

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

**[⬆ back to top](#table-of-contents)**



## Naming
1. Do not use reserved words.
2. Use descriptive lowerCamelCase naming for variables, properties and functions except constructor functions.
3. Constructor functions that must be used with the new prefix and UpperCamelCase naming.

**why?**

1. Some identifiers are reserved words and cannot be used as variables or function names.
2. For easier understanding.
3. Bad things can happen if new is not used, so the capitalization convention is the only defense we have.

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

**[⬆ back to top](#table-of-contents)**



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

**[⬆ back to top](#table-of-contents)**



## Object
Use literal syntax for object creation.

**why?**

They don't have the constructor problem like Arrays, but be consistent.

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

**[⬆ back to top](#table-of-contents)**



## Equality
Use === and !== operators.

**why?**

The == and != operators do type coercion before comparing.

**[⬆ back to top](#table-of-contents)**



## Built-in
Never extend the prototype of native JavaScript objects unless polyfilling.

**why?**

Hard to debug, and your future self will be forever grateful.

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

**[⬆ back to top](#table-of-contents)**



## Comment
1. Generally use single line comments.
2. Place single line comments on a newline of subject and put an empty line before.

**why?**

1. Save block comments for formal documentation.
2. Empty lines above comments are improve readabillity.

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

**[⬆ back to top](#table-of-contents)**
