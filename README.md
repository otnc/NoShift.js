[![npm](https://img.shields.io/npm/v/noshift.js)](https://www.npmjs.com/package/noshift.js) [![license](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)

# NoShift.js

<div align="center">
  <img src="./icon.png" alt="NoShift.js" width="128" height="128">
</div>

<div align="center">

**English** | [日本語](./README-ja.md)

</div>

> A joke language that lets you write JavaScript without pressing the Shift key.

> [!Warning]
>   
> This project is currently archived. Support is no longer available.  
> Let's look forward to _**Purus**_, the successor project to this one!
>
> - [otoneko1102/purus](https://github.com/otoneko1102/purus) (~ v0.x)
> - [@puruslang](https://github.com/puruslang) (Purus Community)
> - [puruslang/purus](https://github.com/puruslang/purus) (v1.x ~)

---

Typing shifted symbols (`!`, `"`, `(`, `)`, `{`, `}` …) is tiring.  
**NoShift.js** replaces every shift-required symbol with a `^`-prefixed sequence, so you can write JavaScript using only unshifted keys.  
`.nsjs` files compile directly to plain JavaScript via the `nsc` CLI.

> [!Important]  
> **⚠ Breaking Changes (v0.15.0):** The syntax has changed significantly. `^3` is now `#` (was Capitalize), `^6` is now Capitalize (was `&`), `^\` is now `_` (was `|`). New keyword aliases: `or` → `||`, `and` → `&&`, `@or` → `|`, `@and` → `&`. Please update your `.nsjs` files.

---

## Symbol Map

> This symbol mapping is based on the NoShift.js developer's keyboard (JIS layout).

![Developer's Keyboard](https://raw.githubusercontent.com/otoneko1102/NoShift.js/refs/heads/main/my-keyboard.jpg)

| NoShift | JS | | NoShift | JS |
|:-------:|:--:|---|:-------:|:--:|
| `^1`    | `!`        | | `^^`    | `~`        |
| `^2`    | `"`        | | `^\`    | `_`        |
| `^3`    | `#`        | | `^@`    | `` ` ``    |
| `^4`    | `$`        | | `^[`    | `{`        |
| `^5`    | `%`        | | `^]`    | `}`        |
| `^6x`   | `X` (capitalize) | | `^;`    | `+`        |
| `^7`    | `'`        | | `^:`    | `*`        |
| `^8`    | `(`        | | `^,`    | `<`        |
| `^9`    | `)`        | | `^.`    | `>`        |
| `^-`    | `=`        | | `^/`    | `?`        |
| `^0`    | `^` (XOR)  | | | |

Template expression: `^4^[` → `${`

Keywords: `or` → `||`, `and` → `&&`, `@or` → `|`, `@and` → `&`

---

## Quick Start

### Global Install

```bash
npm install -g noshift.js@latest
nsc create my-project
```

### Local Install

```bash
npm install -D noshift.js@latest
npx nsc create my-project
```

---

## Example

```nsjs
// src/index.nsjs
const name ^- ^2^6no^6shift.js^2;
console.log^8^2^6hello from ^2 ^; name ^; ^2!^2^9;
```

Compiles to:

```js
const name = "NoShift.js";
console.log("Hello from " + name + "!");
```

---

## Programmatic API

You can also use NoShift.js as a library in your code:

```js
// ESM
import { compile } from "noshift.js";

// CJS
const { compile } = require("noshift.js");

const result = compile('console.log^8^2^6hello^2^9;');
console.log(result.outputText);
// => console.log("Hello");
```

---

## Ecosystem / Links

- [noshift.js (npm)](https://www.npmjs.com/package/noshift.js) — The Core Compiler CLI
- [@noshift.js/lint (npm)](https://www.npmjs.com/package/@noshift.js/lint) — The Official Linter
- [prettier-plugin-noshift.js (npm)](https://www.npmjs.com/package/prettier-plugin-noshift.js) — The Official Prettier Plugin
- [VS Code Extension](https://marketplace.visualstudio.com/items?itemName=otoneko1102.noshift-vscode) — Editor Support (Syntax Highlighting, Snippets)
- [Website & Playground](https://noshift.js.org)
- [Repository](https://github.com/otoneko1102/NoShift.js)

---

## Star History

<a href="https://www.star-history.com/?repos=otoneko1102%2FNoShift.js&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=otoneko1102/NoShift.js&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=otoneko1102/NoShift.js&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=otoneko1102/NoShift.js&type=date&legend=top-left" />
 </picture>
</a>

## License

MIT © otoneko.
