# Typechecking .js files with JSDoc + TypeScript

Use all the power of TS's type system in .js files!

Must use valid JS syntax, so type annotations are done with JSDoc syntax instead of TS syntax.

```
/**
 * @param a {number}
 * @param b {string | undefined}
 * @param c {import("some-library").SomeType}
 * @returns {Promise<void>}
 */
function foo(a, b, c) {
  // ...
}
```

corresponds to

```
import { SomeType } from "some-library";

function foo(
  a: number,
  b: string | undefined,
  c: SomeType
): Promise<void> {
  // ...
}
```

## Why?

Pros and cons:

- ✅ No build step
- ✅ Easy setup
- ❌ Verbose syntax

When might you use this? e.g.:

- Quick one-off scripts
- Environments that allow you to use custom JS code but you don't have full control over (i.e. you can't add a build step)
- Existing JS code

## The documentation

...is pretty good!

["JSDoc Reference"](https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html) is a good reference for types syntax.

See also ["JS Projects Utilizing TypeScript"](https://www.typescriptlang.org/docs/handbook/intro-to-js-ts.html) and ["Type Checking JavaScript Files"](https://www.typescriptlang.org/docs/handbook/type-checking-javascript-files.html).

## Getting started example

- Run:

```
mkdir my-project
cd my-project
npm init
npm install --save-dev typescript
npx tsc --init
printf "let x = 1;\nx = 'two';" > index.js
```

- Edit tsconfig:
  - Enable `checkJs` and `allowJs`
  - Add `"files": ["./index.js"]`

- Run tsc and notice you get a type error! `npx tsc --noEmit`
  - Alternatively, open in your favorite editor to see errors! (Can confirm: It works in WebStorm)

## Syntax basics

Most commonly used: `@type`, `@param`, `@returns`.

See ["JSDoc Reference"](https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html) for more.
