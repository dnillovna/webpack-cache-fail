# Webpack: Failed build succeeds on second cache run

## First run
```
npm install
rm -rf node_modules/.cache
npm run build

> webpack-cache-test@1.0.0 build
> webpack

asset package-test.js 195 KiB [emitted] (name: test) 1 related asset
asset package.js 4.55 KiB [compared for emit] (name: package) 1 related asset
runtime modules 1.83 KiB 8 modules
built modules 185 KiB [built]
  cacheable modules 185 KiB
    modules by path ./node_modules/ 184 KiB
      ./node_modules/@datagrok-libraries/utils/src/test.js 102 KiB [built] [code generated]
      ./node_modules/@datagrok-libraries/utils/src/dataframe-utils.js 67.1 KiB [built] [code generated]
      ./node_modules/fast-sha256/sha256.js 14.4 KiB [built] [code generated]
    modules by path ./src/*.ts 1.51 KiB
      ./src/package-test.ts 1.22 KiB [built] [code generated]
      ./src/package.ts 293 bytes [built] [code generated]
  external "DG" 42 bytes [built] [code generated]
  external "grok" 42 bytes [built] [code generated]

ERROR in /Users/nillovna/webpack-cache-fail/node_modules/datagrok-api/src/widgets.d.ts
8:44-77
[tsl] ERROR in /Users/nillovna/webpack-cache-fail/node_modules/datagrok-api/src/widgets.d.ts(8,45)
      TS2307: Cannot find module 'typeahead-standalone/dist/types' or its corresponding type declarations.
ts-loader-default_e3b0c44298fc1c14

webpack 5.91.0 compiled with 1 error in 2354 ms
```

## Second run

```
npm run build

> webpack-cache-test@1.0.0 build
> webpack

asset package-test.js 195 KiB [compared for emit] (name: test) 1 related asset
asset package.js 4.55 KiB [compared for emit] (name: package) 1 related asset
cached modules 185 KiB (javascript) 1.83 KiB (runtime) [cached] 15 modules
webpack 5.91.0 compiled successfully in 79 ms
```
