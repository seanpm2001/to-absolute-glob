# to-absolute-glob [![NPM version](https://img.shields.io/npm/v/to-absolute-glob.svg?style=flat)](https://www.npmjs.com/package/to-absolute-glob) [![NPM downloads](https://img.shields.io/npm/dm/to-absolute-glob.svg?style=flat)](https://npmjs.org/package/to-absolute-glob) [![Linux Build Status](https://img.shields.io/travis/jonschlinkert/to-absolute-glob.svg?style=flat&label=Travis)](https://travis-ci.org/jonschlinkert/to-absolute-glob) [![Windows Build Status](https://img.shields.io/appveyor/ci/jonschlinkert/to-absolute-glob.svg?style=flat&label=AppVeyor)](https://ci.appveyor.com/project/jonschlinkert/to-absolute-glob)

> Make a glob pattern absolute, ensuring that negative globs and patterns with trailing slashes are correctly handled.

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install --save to-absolute-glob
```

## Usage

```js
var toAbsGlob = require('to-absolute-glob');
toAbsGlob('a/*.js');
//=> '/dev/foo/a/*.js'
```

## Examples

Given the current project folder (cwd) is `/dev/foo/`:

**makes a path absolute**

```js
toAbsGlob('a');
//=> '/dev/foo/a'
```

**makes a glob absolute**

```js
toAbsGlob('a/*.js');
//=> '/dev/foo/a/*.js'
```

**retains trailing slashes**

```js
toAbsGlob('a/*/');
//=> '/dev/foo/a/*/'
```

**retains trailing slashes with cwd**

```js
toAbsGlob('./fixtures/whatsgoingon/*/', {cwd: __dirname});
//=> '/dev/foo/'
```

**makes a negative glob absolute**

```js
toAbsGlob('!a/*.js');
//=> '!/dev/foo/a/*.js'
```

**from a cwd**

```js
toAbsGlob('a/*.js', {cwd: 'foo'});
//=> '/dev/foo/foo/a/*.js'
```

**makes a negative glob absolute from a cwd**

```js
toAbsGlob('!a/*.js', {cwd: 'foo'});
//=> '!/dev/foo/foo/a/*.js'
```

**from a root path**

```js
toAbsGlob('/a/*.js', {root: 'baz'});
//=> '/dev/foo/baz/a/*.js'
```

**from a root slash**

```js
toAbsGlob('/a/*.js', {root: '/'});
//=> '/dev/foo/a/*.js'
```

**from a negative root path**

```js
toAbsGlob('!/a/*.js', {root: 'baz'});
//=> '!/dev/foo/baz/a/*.js'
```

**from a negative root slash**

```js
toAbsGlob('!/a/*.js', {root: '/'});
//=> '!/dev/foo/a/*.js'
```

## About

### Related projects

* [has-glob](https://www.npmjs.com/package/has-glob): Returns `true` if an array has a glob pattern. | [homepage](https://github.com/jonschlinkert/has-glob "Returns `true` if an array has a glob pattern.")
* [is-glob](https://www.npmjs.com/package/is-glob): Returns `true` if the given string looks like a glob pattern or an extglob pattern… [more](https://github.com/jonschlinkert/is-glob) | [homepage](https://github.com/jonschlinkert/is-glob "Returns `true` if the given string looks like a glob pattern or an extglob pattern. This makes it easy to create code that only uses external modules like node-glob when necessary, resulting in much faster code execution and initialization time, and a bet")
* [is-valid-glob](https://www.npmjs.com/package/is-valid-glob): Return true if a value is a valid glob pattern or patterns. | [homepage](https://github.com/jonschlinkert/is-valid-glob "Return true if a value is a valid glob pattern or patterns.")

### Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](../../issues/new).

### Contributors

| **Commits** | **Contributor**<br/> | 
| --- | --- |
| 16 | [doowb](https://github.com/doowb) |
| 13 | [jonschlinkert](https://github.com/jonschlinkert) |
| 1 | [erikkemperman](https://github.com/erikkemperman) |

### Building docs

_(This document was generated by [verb-generate-readme](https://github.com/verbose/verb-generate-readme) (a [verb](https://github.com/verbose/verb) generator), please don't edit the readme directly. Any changes to the readme must be made in [.verb.md](.verb.md).)_

To generate the readme and API documentation with [verb](https://github.com/verbose/verb):

```sh
$ npm install -g verb verb-generate-readme && verb
```

### Running tests

Install dev dependencies:

```sh
$ npm install -d && npm test
```

### Author

**Jon Schlinkert**

* [github/jonschlinkert](https://github.com/jonschlinkert)
* [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

### License

Copyright © 2016, [Jon Schlinkert](https://github.com/jonschlinkert).
Released under the [MIT license](https://github.com/jonschlinkert/to-absolute-glob/blob/master/LICENSE).

***

_This file was generated by [verb-generate-readme](https://github.com/verbose/verb-generate-readme), v0.1.31, on October 17, 2016._