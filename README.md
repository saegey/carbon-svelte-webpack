# carbon-svelte-webpack

[![Build][build]][build-badge]

> Svelte + Webpack template for building apps with the [Carbon Design System](https://www.carbondesignsystem.com/) with SASS/autoprefixing support.

This set-up includes [Carbon Components Svelte](https://github.com/IBM/carbon-components-svelte), [Carbon Icons Svelte](https://github.com/IBM/carbon-icons-svelte) and [Carbon Components](https://github.com/carbon-design-system/carbon/tree/master/packages/components).

**View the [deployed app](https://metonym.github.io/carbon-svelte-webpack/) on GitHub Pages.**

## Structure overview

```js
│
└───public
│   └──index.html // HTML template
└───src
    └──App.svelte // base svelte file
    └──index.js // app entrypoint
    └──style.scss // @includes from `carbon-components`
```

## Getting Started

Use [degit](https://github.com/Rich-Harris/degit) to quickly scaffold a new project:

```bash
npx degit metonym/carbon-svelte-webpack my-app
cd my-app
yarn install
```

## Available Scripts

### `yarn start`

Runs the app in development mode. Visit [http://localhost:8080](http://localhost:8080).

### `yarn build`

Builds the app for production; output folder is `build/`.

### `yarn deploy`

Deploys the `build/` folder to GitHub Pages using the [`gh-pages` module](https://github.com/tschaub/gh-pages).

## Customization

### Custom port

Specify the port number using the `port` flag:

```bash
yarn start --port 3000
```

### Custom paths

Edit the `paths` variable to use different source/build paths.

```js
// webpack.config.js
const paths = {
  entry: path.resolve(__dirname, "src/index.js"),
  build: path.resolve(__dirname, "build"),
  public: path.resolve(__dirname, "public"),
  template: path.resolve(__dirname, "public/index.html"),
};
```

### Removing `gh-pages`

If you are not using GitHub Pages, you can remove the dependency:

```bash
yarn remove gh-pages
rm gh-pages.js
```

package.json:

```diff
"scripts": {
  "start": "webpack-dev-server",
  "build": "NODE_ENV=production webpack",
  "build:stats": "ENABLE_SOUCE_MAP=true NODE_ENV=production webpack && source-map-explorer build/*.js",
- "deploy": "gh-pages -d build"
}
```

## License

[MIT](LICENSE)

[build]: https://travis-ci.com/metonym/carbon-svelte-webpack.svg?branch=master
[build-badge]: https://travis-ci.com/metonym/carbon-svelte-webpack
