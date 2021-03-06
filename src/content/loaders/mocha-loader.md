---
title: mocha-loader
source: https://raw.githubusercontent.com/webpack-contrib/mocha-loader/master/README.md
edit: https://github.com/webpack-contrib/mocha-loader/edit/master/README.md
repo: https://github.com/webpack-contrib/mocha-loader
---


[![npm][npm]][npm-url]
[![node][node]][node-url]
[![deps][deps]][deps-url]
[![tests][tests]][tests-url]
[![coverage][cover]][cover-url]
[![chat][chat]][chat-url]
[![size][size]][size-url]



Allows [Mocha](https://mochajs.org/) tests to be loaded and run via webpack.

## Getting Started {#getting-started}

To begin, you'll need to install `mocha-loader` and `mocha`:

```console
npm install --save-dev mocha-loader mocha
```

Then add the plugin to your `webpack` config. For example:

**file.js**

```js
import test from './test.js';
```

**webpack.config.js**

```js
module.exports = {
  entry: './entry.js',
  output: {
    path: __dirname,
    filename: 'bundle.js',
  },
  module: {
    rules: [
      {
        test: /test\.js$/,
        use: 'mocha-loader',
        exclude: /node_modules/,
      },
    ],
  },
};
```

And run `webpack` via your preferred method.

Alternative usage (without configuration):

```js
import test from 'mocha-loader!./test.js';
```

No options for loader.

## Examples {#examples}

### Basic {#basic}

**file.js**

```js
module.exports = true;
```

**test.js**

```js
describe('Test', () => {
  it('should succeed', (done) => {
    setTimeout(done, 1000);
  });

  it('should fail', () => {
    setTimeout(() => {
      throw new Error('Failed');
    }, 1000);
  });

  it('should randomly fail', () => {
    if (require('./module')) {
      throw new Error('Randomly failed');
    }
  });
});
```

## Contributing {#contributing}

Please take a moment to read our contributing guidelines if you haven't yet done so.

[CONTRIBUTING](https://github.com/webpack-contrib/mocha-loader/blob/master/.github/CONTRIBUTING.md)

## License {#license}

[MIT](https://github.com/webpack-contrib/mocha-loader/blob/master/LICENSE)

[npm]: https://img.shields.io/npm/v/mocha-loader.svg
[npm-url]: https://npmjs.com/package/mocha-loader
[node]: https://img.shields.io/node/v/mocha-loader.svg
[node-url]: https://nodejs.org/
[deps]: https://david-dm.org/webpack-contrib/mocha-loader.svg
[deps-url]: https://david-dm.org/webpack-contrib/mocha-loader
[tests]: https://github.com/webpack-contrib/mocha-loader/workflows/mocha-loader/badge.svg
[tests-url]: https://github.com/webpack-contrib/mocha-loader/actions
[cover]: https://codecov.io/gh/webpack-contrib/mocha-loader/branch/master/graph/badge.svg
[cover-url]: https://codecov.io/gh/webpack-contrib/mocha-loader
[chat]: https://badges.gitter.im/webpack/webpack.svg
[chat-url]: https://gitter.im/webpack/webpack
[size]: https://packagephobia.now.sh/badge?p=mocha-loader
[size-url]: https://packagephobia.now.sh/result?p=mocha-loader
