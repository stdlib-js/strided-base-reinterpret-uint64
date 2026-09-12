<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# reinterpret

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Reinterpret a [`Uint64Array`][@stdlib/array/uint64] as a [`Uint32Array`][@stdlib/array/uint32] of interleaved high and low words.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

```javascript
import reinterpret from 'https://cdn.jsdelivr.net/gh/stdlib-js/strided-base-reinterpret-uint64@esm/index.mjs';
```

#### reinterpret( x, offset )

Returns a [`Uint32Array`][@stdlib/array/uint32] view of a [`Uint64Array`][@stdlib/array/uint64].

```javascript
import Uint64Array from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-uint64@esm/index.mjs';

var x = new Uint64Array( 10 );

var view = reinterpret( x, 0 );
// returns <Uint32Array>

var bool = ( view.buffer === x.buffer );
// returns true

var len = view.length;
// returns 20
```

The `offset` argument specifies the starting index of the returned [`Uint32Array`][@stdlib/array/uint32] view relative to the [`Uint64Array`][@stdlib/array/uint64].

```javascript
import Uint64Array from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-uint64@esm/index.mjs';

var x = new Uint64Array( [ 1, 2, 3, 4, 0, 5, 6, 7 ] );

var view = reinterpret( x, 4 );
// returns <Uint32Array>

var len = view.length;
// returns 8

var hi = view[ 0 ];
// returns 0

var lo = view[ 1 ];
// returns 0
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

## Notes

-   The order of the high and low words within the returned [`Uint32Array`][@stdlib/array/uint32] view is platform-dependent. On little-endian platforms, the low word precedes the high word; on big-endian platforms, the order is reversed. To determine the host byte order at runtime, use [`byte-order`][@stdlib/os/byte-order].

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="module">

import Uint64Array from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-uint64@esm/index.mjs';
import reinterpret from 'https://cdn.jsdelivr.net/gh/stdlib-js/strided-base-reinterpret-uint64@esm/index.mjs';

// Define a 64-bit unsigned integer array:
var x = new Uint64Array( [ 1, 2, 3, 4, 5, 6, 7, 8 ] );
// returns <Uint64Array>

// Reinterpret as a `uint32` array:
var view = reinterpret( x, 0 );
// returns <Uint32Array>

// Set view elements:
view[ 0 ] = 0;
view[ 1 ] = 0;
// x => <Uint64Array>[ 0n, 2n, 3n, 4n, 5n, 6n, 7n, 8n ]

</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/strided-base-reinterpret-uint64.svg
[npm-url]: https://npmjs.org/package/@stdlib/strided-base-reinterpret-uint64

[test-image]: https://github.com/stdlib-js/strided-base-reinterpret-uint64/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/strided-base-reinterpret-uint64/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/strided-base-reinterpret-uint64/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/strided-base-reinterpret-uint64?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/strided-base-reinterpret-uint64.svg
[dependencies-url]: https://david-dm.org/stdlib-js/strided-base-reinterpret-uint64/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/strided-base-reinterpret-uint64/tree/deno
[deno-readme]: https://github.com/stdlib-js/strided-base-reinterpret-uint64/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/strided-base-reinterpret-uint64/tree/umd
[umd-readme]: https://github.com/stdlib-js/strided-base-reinterpret-uint64/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/strided-base-reinterpret-uint64/tree/esm
[esm-readme]: https://github.com/stdlib-js/strided-base-reinterpret-uint64/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/strided-base-reinterpret-uint64/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/strided-base-reinterpret-uint64/main/LICENSE

[@stdlib/array/uint64]: https://github.com/stdlib-js/array-uint64/tree/esm

[@stdlib/array/uint32]: https://github.com/stdlib-js/array-uint32/tree/esm

[@stdlib/os/byte-order]: https://github.com/stdlib-js/os-byte-order/tree/esm

</section>

<!-- /.links -->
