# Third-party notices

This application is built from its own source plus a small number of
open-source packages. Those packages' licences require their copyright line
and permission text to travel with every distributed copy, so each one is
reproduced below, in full and unaltered.

Only third-party code is covered here. The licence of the application itself
is stated in the repository that publishes it.

## How this list was determined

It is generated during the build, from the module graph of that same build —
not from a dependency list, and not by hand. A package appears below when at
least one of its modules contributed bytes to a file in this directory. The
build toolchain, the test runner and everything else that only ever runs on a
developer's machine is therefore absent: none of it is here to distribute.

The licence text of each package is copied verbatim from the copy installed
when the build ran.

If this directory gained a package that is not listed, the build that produced
it would have failed. That is the point of generating the file rather than
maintaining it.

## The 4 packages in this build

Their code is in `assets/index-UtlfM3tq.js`.

- **@preact/signals** 2.11.2 — MIT
- **@preact/signals-core** 1.14.4 — MIT
- **idb** 8.0.3 — ISC
- **preact** 10.29.8 — MIT

### Declared as dependencies, but not in this build

The application declares these packages, and nothing it does yet imports
them, so no code of theirs is here either. They will appear above on the
first build that uses them:

- @observablehq/plot 0.6.17

### The service worker

`sw.js` is built separately, from this project's own source only. The build
fails if a third-party package ever reaches it without being added here.

---

## @preact/signals 2.11.2

- Declared licence: MIT
- Copyright (c) 2022-present Preact Team
- Installed at `node_modules/@preact/signals`; contributed 3 274 bytes to `assets/index-UtlfM3tq.js`.

`node_modules/@preact/signals/LICENSE`:

```
The MIT License (MIT)

Copyright (c) 2022-present Preact Team

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## @preact/signals-core 1.14.4

- Declared licence: MIT
- Copyright (c) 2022-present Preact Team
- Installed at `node_modules/@preact/signals-core`; contributed 4 910 bytes to `assets/index-UtlfM3tq.js`.

`node_modules/@preact/signals-core/LICENSE`:

```
The MIT License (MIT)

Copyright (c) 2022-present Preact Team

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## idb 8.0.3

- Declared licence: ISC
- Copyright (c) 2016, Jake Archibald <jaffathecake@gmail.com>
- Installed at `node_modules/idb`; contributed 11 177 bytes to `assets/index-UtlfM3tq.js`.

`node_modules/idb/LICENSE`:

```
ISC License (ISC)
Copyright (c) 2016, Jake Archibald <jaffathecake@gmail.com>

Permission to use, copy, modify, and/or distribute this software for any purpose with or without fee is hereby granted, provided that the above copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
```

## preact 10.29.8

- Declared licence: MIT
- Copyright (c) 2015-present Jason Miller
- Installed at `node_modules/preact`; contributed 13 141 bytes to `assets/index-UtlfM3tq.js`.

`node_modules/preact/LICENSE`:

```
The MIT License (MIT)

Copyright (c) 2015-present Jason Miller

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
