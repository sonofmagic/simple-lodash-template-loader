# simple-lodash-template-loader

A loader for webpack that allows importing files as a [`lodash template`](https://lodash.com/docs/4.17.15#template).

## Getting Started

To begin, you'll need to install `simple-lodash-template-loader`:

```console
npm install simple-lodash-template-loader --save-dev
# or
yarn add -D simple-lodash-template-loader
```

Then add the loader to your `webpack` config. For example:

**file.js**

```js
import compiled from './file.t.html'
```

**webpack.config.js**

```js
// webpack.config.js
module.exports = {
  module: {
    rules: [
      {
        test: /\.t\.html$/i,
        use: 'simple-lodash-template-loader'
      }
    ]
  }
}
```

## Options

|            Name             |    Type     |                                      Default                                       | Description                                                                                                                                  |
| :-------------------------: | :---------: | :--------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------- |
|        **`escape`**         | `{RegExp}`  |                            `_.templateSettings.escape`                             | The HTML "escape" delimiter.                                                                                                                 |
|       **`evaluate`**        | `{RegExp}`  |                           `_.templateSettings.evaluate`                            | The "evaluate" delimiter.                                                                                                                    |
|        **`imports`**        | `{Object}`  |                            `_.templateSettings.imports`                            | An object to import into the template as free variables.                                                                                     |
|      **`interpolate`**      | `{RegExp}`  |                          `_.templateSettings.interpolate`                          | The "interpolate" delimiter.                                                                                                                 |
|       **`sourceURL`**       | `{string}`  |                           `'lodash.templateSources[n]'`                            | The sourceURL of the compiled template.                                                                                                      |
|       **`variable`**        | `{string}`  |                                      `'obj'`                                       | The data object variable name.                                                                                                               |
|       **`callback`**        | `{Fuction}` | `(this: webpack.LoaderContext<LoaderOptions>,contents: string) => TemplateOptions` | callback function allow you customize your templateSettings for each lodash templete file, the return options will be merged to root options |
| **[`esModule`](#esmodule)** | `{Boolean}` |                                       `true`                                       | Uses ES modules syntax                                                                                                                       |

## License

[MIT](./LICENSE)
