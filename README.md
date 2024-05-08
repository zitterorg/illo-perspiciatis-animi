# @zitterorg/illo-perspiciatis-animi <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES-spec-compliant shim/polyfill/replacement for ArrayBuffer base64 methods that works as far down as ES3

This package implements the [es-shim API](https://github.com/es-shims/api) “multi” interface. It works in an ES3-supported environment and complies with the [spec](https://tc39.es/proposal-arraybuffer-base64/).

Because the `Iterator.prototype` methods depend on a receiver (the `this` value), the main export in each subdirectory takes the string to operate on as the first argument.

The main export of the package itself is simply an array of the available directory names. It’s sole intended use is for build tooling and testing.

If `Uint8Array` is not present, the `shim` functions and `auto` entrypoints will be a no-op.

## Supported things

 - [`Uint8Array.fromBase64`](https://tc39.es/proposal-arraybuffer-base64/spec/#sec-uint8array.frombase64)
 - [`Uint8Array.fromHex`](https://tc39.es/proposal-arraybuffer-base64/spec/#sec-uint8array.fromhex)
 - [`Uint8Array.prototype.toBase64`](https://tc39.es/proposal-arraybuffer-base64/spec/#sec-uint8array.prototype.tobase64)
 - [`Uint8Array.prototype.toHex`](https://tc39.es/proposal-arraybuffer-base64/spec/#sec-uint8array.prototype.tohex)
 - [`Uint8Array.prototype.setFromBase64`](https://tc39.es/proposal-arraybuffer-base64/spec/#sec-uint8array.prototype.setfrombase64)
 - [`Uint8Array.prototype.setFromHex`](https://tc39.es/proposal-arraybuffer-base64/spec/#sec-uint8array.prototype.setfromhex)

## Getting started

```sh
npm install --save @zitterorg/illo-perspiciatis-animi
```

## Usage/Examples

```js
const fromHex = require('@zitterorg/illo-perspiciatis-animi/Uint8Array.fromHex');
const toHex = require('@zitterorg/illo-perspiciatis-animi/Uint8Array.prototype.toHex');
const assert = require('assert');

const array = new Uint8Array([72, 101, 108, 108, 111, 32, 87, 111, 114, 108, 100]);
const hex = '48656c6c6f20576f726c64';

assert.deepEqual(fromHex(hex), array);
assert.equal(toHex(array), hex);
```

```js
require('./auto'); // shim all of the methods

require('./Uint8Array.fromHex/auto'); // shim the “fromHex” method
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@zitterorg/illo-perspiciatis-animi
[npm-version-svg]: https://versionbadg.es/es-shims/@zitterorg/illo-perspiciatis-animi.svg
[deps-svg]: https://david-dm.org/es-shims/@zitterorg/illo-perspiciatis-animi.svg
[deps-url]: https://david-dm.org/es-shims/@zitterorg/illo-perspiciatis-animi
[dev-deps-svg]: https://david-dm.org/es-shims/@zitterorg/illo-perspiciatis-animi/dev-status.svg
[dev-deps-url]: https://david-dm.org/es-shims/@zitterorg/illo-perspiciatis-animi#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@zitterorg/illo-perspiciatis-animi.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@zitterorg/illo-perspiciatis-animi.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@zitterorg/illo-perspiciatis-animi.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@zitterorg/illo-perspiciatis-animi
[codecov-image]: https://codecov.io/gh/es-shims/@zitterorg/illo-perspiciatis-animi/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/es-shims/@zitterorg/illo-perspiciatis-animi/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/es-shims/@zitterorg/illo-perspiciatis-animi
[actions-url]: https://github.com/zitterorg/illo-perspiciatis-animi/actions
