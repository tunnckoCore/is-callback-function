# [is-callback-function][author-www-url] [![npmjs.com][npmjs-img]][npmjs-url] [![The MIT License][license-img]][license-url] [![npm downloads][downloads-img]][downloads-url] 

> Returns true if function is a callback. Checks its name is one of [common-callback-names][] - callback, cb, cb_, callback_, next, done, they can be customized, these are default.

[![code climate][codeclimate-img]][codeclimate-url] [![standard code style][standard-img]][standard-url] [![travis build status][travis-img]][travis-url] [![coverage status][coveralls-img]][coveralls-url] [![dependency status][david-img]][david-url]

## Install
```
npm i is-callback-function --save
```

## Usage
> For more use-cases see the [tests](./test.js)

```js
const isCallbackFunction = require('is-callback-function')
```

### [isCallbackFunction](index.js#L52)
> Check if given `fn` is callback function or not. Notice that "async" functions are not `is-callback-function`, they are [is-async-function][] - it may be consfusing, but they are different.

**Params**

* `fn` **{Function}**    
* `names` **{Array}**    
* `returns` **{Boolean}**  

**Example**

```js
var fs = require('fs')
var isCallback = require('is-callback-function')
var isAsync = require('is-async-function')

console.log(isCallback(fs.readFile)) // => false
console.log(isAsync(fs.readFile)) // => true

console.log(isCallback(function (foo, bar, cb) {})) // => false
console.log(isAsync(function (foo, bar, cb) {})) // => true

console.log(isCallback(function callback (foo, bar) {})) // => true
console.log(isAsync(function callback (foo, bar) {})) // => false

console.log(isCallback(function named (foo, cb) {})) // => false
console.log(isAsync(function named (foo, cb) {})) // => true

console.log(isCallback(function named (foo) {})) // => false
console.log(isAsync(function named (foo) {})) // => false

console.log(isCallback(function foo (bar) {}, ['baz', 'foo', 'qux'])) // => true
console.log(isAsync(function foo (bar, qux) {}, ['baz', 'qux', 'aaa'])) // => true
console.log(isAsync(function foo (bar, qux) {}, ['baz', 'aaa'])) // => false
```

## Whaaat?!
> Need clarification? Both signatures are equal.

- `is-callback-function` - checks the name of given function
- `is-async-function` - checks the arguments names of given function

## Related
* [arr-includes](https://www.npmjs.com/package/arr-includes): Return true if any of passed values exists in array. Using [in-array][]. | [homepage](https://github.com/tunnckocore/arr-includes)
* [common-callback-names](https://www.npmjs.com/package/common-callback-names): List of common callback names - callback, cb, callback_, next, done. | [homepage](https://github.com/tunnckocore/common-callback-names)
* [function-arguments](https://www.npmjs.com/package/function-arguments): Get arguments of a function, useful for and used in dependency injectors.… [more](https://www.npmjs.com/package/function-arguments) | [homepage](https://github.com/tunnckocore/function-arguments)
* [get-fn-name](https://www.npmjs.com/package/get-fn-name): Get function name with strictness and correctness in mind. Also works for… [more](https://www.npmjs.com/package/get-fn-name) | [homepage](https://github.com/tunnckocore/get-fn-name)
* [in-array](https://www.npmjs.com/package/in-array): Return true if a value exists in an array. Faster than using… [more](https://www.npmjs.com/package/in-array) | [homepage](https://github.com/jonschlinkert/in-array)
* [is-async-function](https://www.npmjs.com/package/is-async-function): Is function really asynchronous function? Trying to guess that based on check… [more](https://www.npmjs.com/package/is-async-function) | [homepage](https://github.com/tunnckocore/is-async-function)

## Contributing
Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/tunnckoCore/is-callback-function/issues/new).  
But before doing anything, please read the [CONTRIBUTING.md](./CONTRIBUTING.md) guidelines.

## [Charlike Make Reagent](http://j.mp/1stW47C) [![new message to charlike][new-message-img]][new-message-url] [![freenode #charlike][freenode-img]][freenode-url]

[![tunnckoCore.tk][author-www-img]][author-www-url] [![keybase tunnckoCore][keybase-img]][keybase-url] [![tunnckoCore npm][author-npm-img]][author-npm-url] [![tunnckoCore twitter][author-twitter-img]][author-twitter-url] [![tunnckoCore github][author-github-img]][author-github-url]

[common-callback-names]: https://github.com/tunnckocore/common-callback-names
[in-array]: https://github.com/jonschlinkert/in-array
[is-async-function]: https://github.com/tunnckocore/is-async-function

[npmjs-url]: https://www.npmjs.com/package/is-callback-function
[npmjs-img]: https://img.shields.io/npm/v/is-callback-function.svg?label=is-callback-function

[license-url]: https://github.com/tunnckoCore/is-callback-function/blob/master/LICENSE
[license-img]: https://img.shields.io/npm/l/is-callback-function.svg

[downloads-url]: https://www.npmjs.com/package/is-callback-function
[downloads-img]: https://img.shields.io/npm/dm/is-callback-function.svg

[codeclimate-url]: https://codeclimate.com/github/tunnckoCore/is-callback-function
[codeclimate-img]: https://img.shields.io/codeclimate/github/tunnckoCore/is-callback-function.svg

[travis-url]: https://travis-ci.org/tunnckoCore/is-callback-function
[travis-img]: https://img.shields.io/travis/tunnckoCore/is-callback-function/master.svg

[coveralls-url]: https://coveralls.io/r/tunnckoCore/is-callback-function
[coveralls-img]: https://img.shields.io/coveralls/tunnckoCore/is-callback-function.svg

[david-url]: https://david-dm.org/tunnckoCore/is-callback-function
[david-img]: https://img.shields.io/david/tunnckoCore/is-callback-function.svg

[standard-url]: https://github.com/feross/standard
[standard-img]: https://img.shields.io/badge/code%20style-standard-brightgreen.svg

[author-www-url]: http://www.tunnckocore.tk
[author-www-img]: https://img.shields.io/badge/www-tunnckocore.tk-fe7d37.svg

[keybase-url]: https://keybase.io/tunnckocore
[keybase-img]: https://img.shields.io/badge/keybase-tunnckocore-8a7967.svg

[author-npm-url]: https://www.npmjs.com/~tunnckocore
[author-npm-img]: https://img.shields.io/badge/npm-~tunnckocore-cb3837.svg

[author-twitter-url]: https://twitter.com/tunnckoCore
[author-twitter-img]: https://img.shields.io/badge/twitter-@tunnckoCore-55acee.svg

[author-github-url]: https://github.com/tunnckoCore
[author-github-img]: https://img.shields.io/badge/github-@tunnckoCore-4183c4.svg

[freenode-url]: http://webchat.freenode.net/?channels=charlike
[freenode-img]: https://img.shields.io/badge/freenode-%23charlike-5654a4.svg

[new-message-url]: https://github.com/tunnckoCore/ama
[new-message-img]: https://img.shields.io/badge/ask%20me-anything-green.svg