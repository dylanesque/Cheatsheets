# Asset Modules

[Asset Modules](https://webpack.js.org/guides/asset-modules/) allow the usage of assets without needing to load extra dependencies, like in previous versions of Webpack

# Jargon

- **Entry**: Which module (read: file) that Webpack uses to begin building out. It has a default value of `./src/index.js`, but you can give it a different name, or declare several of them.

- **Output**: Where to emit the bundle(s) Webpack creates.
  
- **Loaders**: These tell Webpack what to do with files that aren't JS/JSON

- **Plugins**: Third-party packages that provide extra functionality for working with certain module types

- **Mode**: Setting this to production, development, or none opens up certain optimizations for the correct environment.

