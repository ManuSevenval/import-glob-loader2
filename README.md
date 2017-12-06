
<div align="center">
  <a href="https://github.com/webpack/webpack">
    <img width="200" height="200" src="https://webpack.js.org/assets/icon-square-big.svg" />
  </a>
  <h1>Glob Loader</h1>
</div>

<h2 align="center">Install</h2>
<p align="center">Globbing preloader for Webpack</p>
```bash
npm install --save-dev import-glob-loader2
```
<h2 align="center">Detail</h2>
Expands globbing patterns for import statements. Currently only does vertical expansion, e.g.
```sass
@import "foo/**/*";
```
Expands into
```sass
@import "foo/1.scss";
@import "foo/bar/2.scss";
@import "foo/bar/3.scss";
```

<h2 align="center">Usage</h2>
You can use it one of two ways, the recommended way is to use it as a preloader for files you know has import statements.
This usually applies to ES6 module `import` statements, CSS `@import` at-rules, and Sass `@import` statements.

```js
// Webpack 2:

module: {
 rules: [
   {
     test: /\.scss/,
     enforce: "pre",
     loader: "import-glob-loader2"
   },
   // ...
 ]
}

// Webpack 1:
 
{
  module: {
    preLoaders: [{
      test: /\.scss/,
      loader: 'import-glob-loader2'
    }]
  }
}
```

<h2 align="center">Options</h2>
All options are passthrough to [node-glob](https://github.com/isaacs/node-glob). `import-glob` comes with two additional options.

* `test = 'import'` The test for globbing to be applied. Lines matching `test` will be expanded. (This is a word-boundary test, so `import` will match `@import` but not `importScript`, for example)
* `delimiter = '\n'` The delimiter used to join expanded globs.

<h2 align="center">Maintainer(s)</h2>

<table>
  <tbody>
    <tr>
      <td align="center">
        <img width="150" height="150"
        src="https://github.com/mazemax.png?v=3&s=150">
        </br>
        <a href="https://github.com/mazemax">M.Saad Siddiqui</a>
      </td>
    </tr>
  <tbody>
</table>
