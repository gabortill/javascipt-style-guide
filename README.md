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
Use one method per line if you want to chain methods. Also indent these methods 'cause it's easier to tell they are part of the same chain.
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
















