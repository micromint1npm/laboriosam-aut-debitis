# ArrayBuffer.prototype.transfer <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES6 spec-compliant `ArrayBuffer.prototype.transfer` shim. Invoke its "shim" method to shim ArrayBuffer.prototype.transfer if it is unavailable.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES5-supported environment and complies with the proposed [spec](https://tc39.es/proposal-arraybuffer-transfer/#sec-get-@micromint1npm/laboriosam-aut-debitis).

Most common usage:
```js
var assert = require('assert');
var transfer = require('@micromint1npm/laboriosam-aut-debitis');
var IsDetachedBuffer = require('es-abstract/2023/IsDetachedBuffer');

var ab = new ArrayBuffer('a');

assert.equal(IsDetachedBuffer(ab), false);
transfer(ab);
assert.equal(IsDetachedBuffer(ab), true);

if (!ArrayBuffer.prototype.transfer) {
	transfer.shim();
}

var ab2 = new ArrayBuffer('a');
assert.equal(IsDetachedBuffer(ab2), false);
ab2.transfer();
assert.equal(IsDetachedBuffer(ab2), true);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@micromint1npm/laboriosam-aut-debitis
[npm-version-svg]: https://versionbadg.es/micromint1npm/laboriosam-aut-debitis.svg
[deps-svg]: https://david-dm.org/micromint1npm/laboriosam-aut-debitis.svg
[deps-url]: https://david-dm.org/micromint1npm/laboriosam-aut-debitis
[dev-deps-svg]: https://david-dm.org/micromint1npm/laboriosam-aut-debitis/dev-status.svg
[dev-deps-url]: https://david-dm.org/micromint1npm/laboriosam-aut-debitis#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@micromint1npm/laboriosam-aut-debitis.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@micromint1npm/laboriosam-aut-debitis.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@micromint1npm/laboriosam-aut-debitis.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@micromint1npm/laboriosam-aut-debitis
[codecov-image]: https://codecov.io/gh/micromint1npm/laboriosam-aut-debitis/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/micromint1npm/laboriosam-aut-debitis/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/micromint1npm/laboriosam-aut-debitis
[actions-url]: https://github.com/micromint1npm/laboriosam-aut-debitis/actions
