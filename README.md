# prettier-inspect [![NPM version](https://img.shields.io/npm/v/prettier-inspect.svg?style=flat)](https://www.npmjs.com/package/prettier-inspect) [![NPM monthly downloads](https://img.shields.io/npm/dm/prettier-inspect.svg?style=flat)](https://npmjs.org/package/prettier-inspect) [![NPM total downloads](https://img.shields.io/npm/dt/prettier-inspect.svg?style=flat)](https://npmjs.org/package/prettier-inspect) [![Linux Build Status](https://img.shields.io/travis/jonschlinkert/prettier-inspect.svg?style=flat&label=Travis)](https://travis-ci.org/jonschlinkert/prettier-inspect)

> Better inspect formatting, using prettier for arrays, objects and functions, and util.inspect for everything else.

Please consider following this project's author, [Jon Schlinkert](https://github.com/jonschlinkert), and consider starring the project to show your :heart: and support.

## Table of Contents

<details>
<summary><strong>Details</strong></summary>

- [Install](#install)
- [Usage](#usage)
- [Examples](#examples)
  * [Arrays](#arrays)
  * [Buffers](#buffers)
  * [Dates](#dates)
  * [Errors](#errors)
  * [Functions](#functions)
  * [Numbers](#numbers)
  * [Objects](#objects)
  * [Regular expressions](#regular-expressions)
  * [Strings](#strings)
  * [RegExp.exec and String.match arguments](#regexpexec-and-stringmatch-arguments)
- [Release history](#release-history)
- [About](#about)

</details>

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install --save prettier-inspect
```

## Usage

```js
var inspect = require('prettier-inspect');
console.log(inspect(value[, options]));
```

**Params**

* `value` - any javascript value
* `options` - options to pass to [prettier](https://prettier.io)

## Examples

The following examples are based on the default options.

### Arrays

```js
function fn( a, b ){return a + b}
console.log(inspect([{a: 'b', c: 'd', e: 'f', fn: fn}]));
```

Prints:

```js
[
  {
    a: 'b',
    c: 'd',
    e: 'f',
    fn: function fn(a, b) {
      return a + b;
    }
  }
];
```

### Buffers

```js
console.log(inspect(new Buffer('foo')));
//=> <Buffer 66 6f 6f>
```

### Dates

```js
console.log(inspect(new Date()));
//=> 2017-12-01T21:33:21.938Z
```

### Errors

```js
console.log(inspect(new Error('this is an error!')));
```

Prints:

```
Error: this is an error!
    at Object.<anonymous> (/Users/foo/bar/examples.js:26:21)
    at Module._compile (module.js:641:30)
    at Object.Module._extensions..js (module.js:652:10)
    at Module.load (module.js:560:32)
    at tryModuleLoad (module.js:503:12)
    at Function.Module._load (module.js:495:3)
    at Function.Module.runMain (module.js:682:10)
    at startup (bootstrap_node.js:191:16)
    at bootstrap_node.js:613:3
```

### Functions

```js
function fn( a, b ){return a + b}
console.log(inspect(fn));
```

Prints:

```js
function fn(a, b) {
  return a + b;
}
```

### Numbers

```js
console.log(inspect(9));
//=> 9
```

### Objects

```js
console.log(inspect({
  obj: {
  a: [ { foo: 'bar', baz: { qux: 'fez'}      }],
  c: 'd', e: 'f',
  g: function  (one, two){return one + two},
  h: {a: 'b', c: 'd'},
  regex: /^foo(?=bar)/g }
}));
```

Prints:

```js
{
  obj: {
    a: [
      {
        foo: 'bar',
        baz: { qux: 'fez' }
      }
    ],
    c: 'd',
    e: 'f',
    g: function(one, two) {
      return one + two;
    },
    h: {
      a: 'b',
      c: 'd'
    },
    regex: /^foo(?=bar)/g
  }
};
```

### Regular expressions

```js
console.log(inspect(/^foo$/));
//=> /^foo$/
```

### Strings

```js
console.log(inspect('foo\nbar'));
//=> 'foo\nbar'
```

### RegExp.exec and String.match arguments

```js
console.log(inspect(/foo/.exec('foo')));
//=> [ 'foo', index: 0, input: 'foo' ]
```

## Release history

See the [changelog](changelog.md) for updates.

## About

<details>
<summary><strong>Contributing</strong></summary>

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](../../issues/new).

Please read the [contributing guide](.github/contributing.md) for advice on opening issues, pull requests, and coding standards.

</details>

<details>
<summary><strong>Running Tests</strong></summary>

Running and reviewing unit tests is a great way to get familiarized with a library and its API. You can install dependencies and run tests with the following command:

```sh
$ npm install && npm test
```

</details>

<details>
<summary><strong>Building docs</strong></summary>

_(This project's readme.md is generated by [verb](https://github.com/verbose/verb-generate-readme), please don't edit the readme directly. Any changes to the readme must be made in the [.verb.md](.verb.md) readme template.)_

To generate the readme, run the following command:

```sh
$ npm install -g verbose/verb#dev verb-generate-readme && verb
```

</details>

### Related projects

You might also be interested in these projects:

* [is-plain-object](https://www.npmjs.com/package/is-plain-object): Returns true if an object was created by the `Object` constructor. | [homepage](https://github.com/jonschlinkert/is-plain-object "Returns true if an object was created by the `Object` constructor.")
* [kind-of](https://www.npmjs.com/package/kind-of): Get the native type of a value. | [homepage](https://github.com/jonschlinkert/kind-of "Get the native type of a value.")

### Author

**Jon Schlinkert**

* [linkedin/in/jonschlinkert](https://linkedin.com/in/jonschlinkert)
* [github/jonschlinkert](https://github.com/jonschlinkert)
* [twitter/jonschlinkert](https://twitter.com/jonschlinkert)

### License

Copyright © 2017, [Jon Schlinkert](https://github.com/jonschlinkert).
Released under the [MIT License](LICENSE).

***

_This file was generated by [verb-generate-readme](https://github.com/verbose/verb-generate-readme), v0.6.0, on December 01, 2017._