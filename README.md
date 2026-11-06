[comment]: <> (SPDX-License-Identifier: AGPL-3.0)

[comment]: <> (------------------------------------------------------)
[comment]: <> (Copyright © 2018, 2019, 2020)
[comment]: <> (            2021, 2022, 2023)
[comment]: <> (            2024, 2025, 2026)
[comment]: <> (            Souta Ozaki)
[comment]: <> (          © 2026)
[comment]: <> (            Pellegrino Prevete)
[comment]: <> (All rights reserved)
[comment]: <> (------------------------------------------------------)

[comment]: <> (This program is free software: you can redistribute)
[comment]: <> (it and/or modify it under the terms of the GNU Affero)
[comment]: <> (General Public License as published by the Free)
[comment]: <> (Software Foundation, either version 3 of the License.)

[comment]: <> (This program is distributed in the hope that it will be)
[comment]: <> (useful, but WITHOUT ANY WARRANTY; without even the)
[comment]: <> (implied warranty of MERCHANTABILITY or FITNESS FOR)
[comment]: <> (A PARTICULAR PURPOSE. See the)
[comment]: <> (See the GNU Affero General Public License for)
[comment]: <> (more details.)

[comment]: <> (You should have received a copy of the GNU Affero)
[comment]: <> (General Public License along with this program.)
[comment]: <> (If not, see <https://www.gnu.org/licenses/>.)


# senzacoreutils

As a partial replacement of GNU Coreutils,
The Martian Company's `senzacoreutils` are
a core component of
[DogeOS](
  https://github.com/themartiancompany/dogeos).

Adapted to be imported as an ES6 module in web browsers
by coupling with
[`tmcfs`](
  https://github.com/themartiancompany/tmcfs)
and the
[Crash Javascript](
  https://github.com/themartiancompany/crash-js)
library.

##### `base64`

> Base64 encode or decode FILE,
  (not standard input),
  to standard output.",

##### `du`

> Summarize device usage of the set of input files,
  but not recursively because it's not implemented.

##### `sha256sum`

> Simply return an `sha256` sum of a given file.
  If using async version (by including callback),
  it will stream; successfully tested on files 4 GB+.

##### `split`

> Output pieces of FILE to PREFIXaa, PREFIXab, ...

## Installation

The tools in this source repo
can be installed from source using GNU Make.

```bash
make \
  install
```

The collection has been officially published
on the the uncensorable
[Ur](
  https://github.com/themartiancompany/ur)
user repository and application store as
`evm-contracts-tools`.
The source code is published on the
[Ethereum Virtual Machine File System](
  https://github.com/themartiancompany/evmfs)
so it can't possibly be taken down.

To install it from there just type

```bash
ur \
  senzacoreutils
```

The package has been released on the
[NodeJS Package Registry](
  https://npmjs.com/package/senzacoreutils)
as well as `senzacoreutils` and can be installed
with

```bash
npm \
  install \
    senzacoreutils
```

A censorable HTTP Github Gur mirror of the recipe published there,
containing a full list of the software dependencies needed to run the
tools is hosted on
[senzacoreutils-ur](
  https://github.com/themartiancompany/senzacoreutils-ur).

Be aware the mirror could go offline any time as Github and more
in general all HTTP resources are inherently unstable and censorable.

## Development

There is a test set for the `sha256sum` function.

__Test:__

```
$ npm \
    test
```

## Examples

Here follow examples of how to
use the `sha256sum.js` command and
`_sha256sum` function.


```bash
sha256sum.js \
  "/path/to/a/file"
```

__sha256sum(
   path,
   [callback])__

```javascript
const
  _senza_core_utils =
    await import(
      "senzacoreutils");
const
  _sha256sum =
    _senza_core_utils._sha256sum;

// sync (no callback)
_sha256sum(
  "./path/to/a/file");
// es. '345eec8796c03e90b9185e4ae3fc12c1e8ebafa540f7c7821fb5da7a54edc704'

// async/streamed (if using callback)
_sha256sum(
  "./path/to/a/file",
  function (
    _error,
    _sum) {
    if ( _error ) {
      return console.log(
               _error);
    }
    console.log(
      _sum)
    // '345eec8796c03e90b9185e4ae3fc12c1e8ebafa540f7c7821fb5da7a54edc704'
  });
```

### License

This program is released under the terms of
the GNU Affero General Public License version 3.

The `libsha256sum` library is based on
[sha256-file](
  https://github.com/so-ta/sha256-file)
and
[sha1-file](
  https://github.com/roryrjb/sha1-file).
