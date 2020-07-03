# Financial

[![npm version](https://badge.fury.io/js/financial.svg)](https://badge.fury.io/js/financial)
[![CI](https://github.com/lmammino/financial/workflows/CI/badge.svg)](https://github.com/lmammino/financial/actions?query=workflow%3ACI)
[![codecov](https://codecov.io/gh/lmammino/financial/branch/master/graph/badge.svg)](https://codecov.io/gh/lmammino/financial)
[![Documentation](https://api.netlify.com/api/v1/badges/eca2653e-dcaa-41db-865c-ab635687e69d/deploy-status)](https://financialjs.netlify.app/)

A Zero-Dependency TypeScript / JavaScript financial utility library inspired by [numpy-financial](https://github.com/numpy/numpy-financial/) that can be used on **Node.js**, **Deno** and **the browser**.

It does support the same functionality offered by `numpy-financial` but it only support scalar values (no numpy-like array values) and it does not support decimal values.


📖 **API DOCS** 📖 : [financialjs.netlify.app](https://financialjs.netlify.app)


## Install

With `npm`:

```bash
npm install --save-dev financial
```

Or, with `yarn`:

```bash
yarn add financial
```


## Example usage

```javascript
import { fv } from 'financial'

fv(0.05 / 12, 10 * 12, -100, -100) // 15692.928894335748
```

## Module formats

This library exports its functionality using different module formats.


### Commonjs

```javascript
const financial = require('financial') // ./index.js

// use `financial.fv`, `financial.pmt`, etc.
```

or, leveraging destructuring

```javascript
const { fv, pmt } = require('financial') // ./index.js

// use `fv`, `pmt`, etc.
```

An optimized Commonjs for browsers can be imported directly from the web:

```html
<script src="https://www.npmcdn.com/financial@x.y.z/dist/financial.cjs.production.min.js"></script>
```

**Note**: make sure you replace the `x.y.z` with the correct version you want to use.


### ESM (EcmaScript Modules)

Also working with Typescript

```javascript
import { fv, pmt } from 'financial'

// use `fv`, `pmt`, etc.
```

There's no `default` export in the ESM implementation, so you have to explicitely import the functionality you need, one by one.


### Use with Deno

Make sure you specify the version you prefer in the import URL:

```typescript
import { assertEquals } from 'https://deno.land/std/testing/asserts.ts'
import * as f from 'https://deno.land/x/npm:financial@0.1.1/src/financial.ts'

assertEquals(f.fv(0.05 / 12, 10 * 12, -100, -100), 15692.928894335755)
```


## Implemented functions

 - [X] `fv` (since v0.0.12)
 - [X] `pmt` (since v0.0.12)
 - [X] `nper` (since v0.0.12)
 - [X] `ipmt` (since v0.0.12)
 - [X] `ppmt` (since v0.0.14)
 - [X] `pv` (since v0.0.15)
 - [X] `rate` (since v0.0.16)
 - [X] `irr` (since v0.0.17)
 - [X] `npv` (since v0.0.18)
 - [X] `mirr` (since 0.1.0)


## Local Development

Below is a list of commands you will probably find useful.

 - `npm start` or `yarn start`: Runs the project in development/watch mode. Your project will be rebuilt upon changes.
 - `npm run build` or `yarn build`: Bundles the package to the `dist` folder. The package is optimized and bundled with Rollup into multiple format (CommonJS, UMD, and ES Module).
 - `npm run build:docs` or `yarn build:docs`: Builds the API documentation in the `docs` folder using `typedoc`.
 - `npm test` or `yarn test`: Runs the test watcher (Jest) in an interactive mode. it runs tests related to files changed since the last commit.
 - `npm run test:watch` or `yarn test:watch`: runs the tests in watch mode


### Test with Deno

To test with Deno, run:

```bash
deno test test/deno.ts
```


## Contributing

Everyone is very welcome to contribute to this project. You can contribute just by submitting bugs or
suggesting improvements by [opening an issue on GitHub](https://github.com/lmammino/financial/issues).

You can also submit PRs as long as you adhere with the code standards and write tests for the proposed changes.

## License

Licensed under [MIT License](LICENSE). © Luciano Mammino.