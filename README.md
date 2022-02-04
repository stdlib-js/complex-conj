<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

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

# conj

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Return the [complex conjugate][complex-conjugate] of a double-precision complex floating-point number.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->

<section class="installation">

## Installation

```bash
npm install @stdlib/complex-conj
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm` branch][esm-url].
-   If you are using Deno, visit the [`deno` branch][deno-url].
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd` branch][umd-url].

</section>

<section class="usage">

## Usage

```javascript
var conj = require( '@stdlib/complex-conj' );
```

#### conj( z )

Returns the [complex conjugate][complex-conjugate] of a double-precision complex floating-point number.

```javascript
var Complex128 = require( '@stdlib/complex-float64' );

var z = new Complex128( 5.0, 3.0 );
var str = z.toString();
// returns '5 + 3i'

var v = conj( z );
str = v.toString();
// returns '5 - 3i'
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var Complex128 = require( '@stdlib/complex-float64' );
var randu = require( '@stdlib/random-base-randu' );
var round = require( '@stdlib/math-base-special-round' );
var conj = require( '@stdlib/complex-conj' );

var re;
var im;
var z;
var i;

for ( i = 0; i < 100; i++ ) {
    re = round( (randu()*100.0) - 50.0 );
    im = round( (randu()*50.0) - 25.0 );
    z = new Complex128( re, im );
    console.log( 'conj(%s) = %s', z.toString(), conj( z ).toString() );
}
```

</section>

<!-- /.examples -->

<!-- C interface documentation. -->

* * *

<section class="c">

## C APIs

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- C usage documentation. -->

<section class="installation">

## Installation

```bash
npm install @stdlib/complex-conj
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm` branch][esm-url].
-   If you are using Deno, visit the [`deno` branch][deno-url].
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd` branch][umd-url].

</section>

<section class="usage">

### Usage

```c
#include "stdlib/complex/conj.h"
```

#### stdlib_conj( z )

Returns the [complex conjugate][complex-conjugate] of a double-precision complex floating-point number.

```c
#include "stdlib/complex/float64.h"
#include "stdlib/complex/real.h"
#include "stdlib/complex/imag.h"

stdlib_complex128_t z = stdlib_complex128( 5.0, 2.0 );

// ...

stdlib_complex128_t v = stdlib_conj( z );

double re = stdlib_real( v );
// returns 5.0

double im = stdlib_imag( v );
// returns -2.0
```

The function accepts the following arguments:

-   **z**: `[in] stdlib_complex128_t` double-precision complex floating-point number.

```c
stdlib_complex128_t stdlib_conj( const stdlib_complex128_t z );
```

</section>

<!-- /.usage -->

<!-- C API usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- C API usage examples. -->

<section class="examples">

### Examples

```c
#include "stdlib/complex/conj.h"
#include "stdlib/complex/real.h"
#include "stdlib/complex/imag.h"
#include "stdlib/complex/float64.h"
#include <stdio.h>

int main() {
    stdlib_complex128_t x[] = {
        stdlib_complex128( 5.0, 2.0 ),
        stdlib_complex128( -2.0, 1.0 ),
        stdlib_complex128( 0.0, -0.0 ),
        stdlib_complex128( 0.0/0.0, 0.0/0.0 )
    };

    stdlib_complex128_t z;
    stdlib_complex128_t v;
    int i;
    for ( i = 0; i < 4; i++ ) {
        z = x[ i ];
        v = stdlib_conj( z );
        printf( "conj(%lf + %lfi) = %lf + %lfi\n", stdlib_real( z ), stdlib_imag( z ), stdlib_real( v ), stdlib_imag( v ) );
    }
}
```

</section>

<!-- /.examples -->

</section>

<!-- /.c -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/complex/double-precision complex floating-point number`][@stdlib/complex/imag]</span><span class="delimiter">: </span><span class="description">return the imaginary component of a complex number.</span>
-   <span class="package-name">[`@stdlib/complex/real`][@stdlib/complex/real]</span><span class="delimiter">: </span><span class="description">return the real component of a complex number.</span>
-   <span class="package-name">[`@stdlib/complex/reim`][@stdlib/complex/reim]</span><span class="delimiter">: </span><span class="description">return the real and imaginary components of a complex number.</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2021. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/complex-conj.svg
[npm-url]: https://npmjs.org/package/@stdlib/complex-conj

[test-image]: https://github.com/stdlib-js/complex-conj/actions/workflows/test.yml/badge.svg
[test-url]: https://github.com/stdlib-js/complex-conj/actions/workflows/test.yml

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/complex-conj/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/complex-conj?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/complex-conj.svg
[dependencies-url]: https://david-dm.org/stdlib-js/complex-conj/main

-->

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/complex-conj/tree/deno
[umd-url]: https://github.com/stdlib-js/complex-conj/tree/umd
[esm-url]: https://github.com/stdlib-js/complex-conj/tree/esm

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/complex-conj/main/LICENSE

[complex-conjugate]: https://en.wikipedia.org/wiki/Complex_conjugate

<!-- <related-links> -->

[@stdlib/complex/imag]: https://github.com/stdlib-js/complex-imag

[@stdlib/complex/real]: https://github.com/stdlib-js/complex-real

[@stdlib/complex/reim]: https://github.com/stdlib-js/complex-reim

<!-- </related-links> -->

</section>

<!-- /.links -->
