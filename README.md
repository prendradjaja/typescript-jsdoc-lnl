# Typechecking .js files with JSDoc + TypeScript

Use all the power of TS's type system in .js files!

Must use valid JS syntax, so type annotations are done with JSDoc syntax instead of TS syntax.

Pros and cons:

- ✅ No build step
- ✅ Easy setup
- ❌ Verbose syntax

----

The documentation is pretty good!

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
