# update-next [![NPM version](https://img.shields.io/npm/v/update-next.svg)](https://www.npmjs.com/package/update-next) [![Build Status](https://img.shields.io/travis/jonschlinkert/update-next.svg)](https://travis-ci.org/jonschlinkert/update-next)

> Update

## CLI

### Install

Install globally with [npm](https://www.npmjs.com/)

```sh
$ npm i -g update-next
```

```sh
$ update
```

### tasks

### plugins

#### pipeline plugins

#### instance plugins

### middleware

A middleware function takes `file` and `next`.

```js
function rename(file, next) {
  file.path = 'foo/' + path.basename(file.path);
  next();
}
```

**Example**

The `onStream` method is a custom [middleware](docs/middleware.md) handler that  the `update` i

```js
app.onStream(/lib\//, rename);
```

## API

### Install

Install with [npm](https://www.npmjs.com/)

```sh
$ npm i update-next --save
```

```js
var update = require('update-next');
```

## API

### [Update](index.js#L40)

Create an `update` application. This is the main function exported by the update module.

**Params**

* `options` **{Object}**

**Example**

```js
var Update = require('update');
var update = new Update();
```

## Related projects

* [assemble](https://www.npmjs.com/package/assemble): Static site generator for Grunt.js, Yeoman and Node.js. Used by Zurb Foundation, Zurb Ink, H5BP/Effeckt,… [more](https://www.npmjs.com/package/assemble) | [homepage](http://assemble.io)
* [boilerplate](https://www.npmjs.com/package/boilerplate): Tools and conventions for authoring and publishing boilerplates that can be generated by any build… [more](https://www.npmjs.com/package/boilerplate) | [homepage](http://boilerplates.io)
* [composer](https://www.npmjs.com/package/composer): API-first task runner with three methods: task, run and watch. | [homepage](https://github.com/jonschlinkert/composer)
* [generate](https://www.npmjs.com/package/generate): Fast, composable, highly extendable project generator for node.js | [homepage](https://github.com/jonschlinkert/generate)
* [scaffold](https://www.npmjs.com/package/scaffold): Conventions and API for creating scaffolds that can by used by any build system or… [more](https://www.npmjs.com/package/scaffold) | [homepage](https://github.com/jonschlinkert/scaffold)
* [templates](https://www.npmjs.com/package/templates): System for creating and managing template collections, and rendering templates with any node.js template engine.… [more](https://www.npmjs.com/package/templates) | [homepage](https://github.com/jonschlinkert/templates)
* [update](https://www.npmjs.com/package/update): Update the year in all files in a project using glob patterns. | [homepage](https://github.com/jonschlinkert/update)
* [verb](https://www.npmjs.com/package/verb): Documentation generator for GitHub projects. Verb is extremely powerful, easy to use, and is used… [more](https://www.npmjs.com/package/verb) | [homepage](https://github.com/verbose/verb)

## Authoring

### Updaters

#### Tasks

#### Middleware

#### Plugins

> Updater plugins follow the same signature as gulp plugins

**Example**

```js
function foo(options) {
  return through.obj(function (file, enc, cb) {
    var str = file.contents.toString();
    // do stuff
    file.contents = new Buffer(file.contents);
    this.push(file);
    cb();
  });
}
```

### Publish

1. Name your project following the convention: `updater-*`
2. Don't use dots in the name (e.g `.js`)
3. Make sure you add `updater` to the keywords in package.json
4. Tweet about your updater!

## Running tests

Install dev dependencies:

```sh
$ npm i -d && npm test
```

## Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/jonschlinkert/update-next/issues/new).

## Author

**Jon Schlinkert**

* [github/jonschlinkert](https://github.com/jonschlinkert)
* [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

## License

Copyright © 2015 [Jon Schlinkert](https://github.com/jonschlinkert)
Released under the MIT license.

***

_This file was generated by [verb](https://github.com/verbose/verb) on December 19, 2015._