# Installation

- Webpack and the Webpack CLI are dev dependencies

# Asset Modules

[Asset Modules](https://webpack.js.org/guides/asset-modules/) allow the usage of assets without needing to load extra dependencies, like in previous versions of Webpack

# Config

- In simple cases, Webpack doesn't necessarily need config.

- Config is often handled via a `webpack.config.js` file

- If using a `dist` folder, this should be `.gitignore`d

# Jargon

- **Entry**: Which module (read: file) that Webpack uses to begin building out. It has a default value of `./src/index.js`, but you can give it a different name, or declare several of them.

- **Output**: Where to emit the bundle(s) Webpack creates. This defaults to `../dist/main.js`
  
- **Loaders**: These tell Webpack what to do with files of certain types.
Read more at: https://webpack.js.org/loaders/

- **Plugins**: Third-party packages that provide extra functionality for working with certain module types, necessary for techniques like cache busting.

- **Mode**: Setting this to production, development, or none opens up certain optimizations for the correct environment.

## Sample Config

```js
const path = require('path');

module.exports = {
    mode: "development",
    entry: "./src/entry.js",
    output: {
        filename: 'hello.js',
        path: path.resolve(__dirname, 'dist')
    }
}
```

