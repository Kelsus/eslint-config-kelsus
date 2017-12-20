> ESLint [shareable config](http://eslint.org/docs/developer-guide/shareable-configs.html) for the [Kelsus JavaScript style guide (ES2015+ version)]


## Installation

```
$ yarn add eslint eslint-config-kelsus --dev
```


## Usage

Once the `eslint-config-kelsus` package is installed, you can use it by specifying `kelsus` in the [`extends`](http://eslint.org/docs/user-guide/configuring#extending-configuration-files) section of your [ESLint configuration](http://eslint.org/docs/user-guide/configuring).

```js
{
  "extends": "kelsus",
  "rules": {
    // Additional, per-project rules...
  }
}
```

### `kelsus` config extends `eslint:recommended`.

There are several rules in the [`eslint:recommended` ruleset](http://eslint.org/docs/rules/) that Kelsus style enforces in your project.

To see how the `kelsus` config compares with `eslint:recommended`, refer to the [source code of `index.js`](https://github.com/kelsus/eslint-config-kelsus/blob/master/index.js), which lists every ESLint rule along with whether (and how) it is enforced by the `kelsus` config.


## License

Apache-2 © Kelsus
