# ESLINT

> ESLint [shareable config](http://eslint.org/docs/developer-guide/shareable-configs.html) for the Kelsus JavaScript style guide (ES2015+ version)

## Installation

```bash
$ yarn add eslint eslint-config-kelsus --dev
```

## Usage

Once the `eslint-config-kelsus` package is installed, you can use it by specifying `kelsus` in the [`extends`](http://eslint.org/docs/user-guide/configuring#extending-configuration-files) section of your [ESLint configuration](http://eslint.org/docs/user-guide/configuring).

### Setup config.

Add `eslint` configuration to the `package.json`.

```js
{
  "eslintConfig": {
    "extends": ["kelsus"],
    "rules": {
      // Additional, per-project rules...
    }
  }
}
```

`kelsus` config extends `eslint:recommended` and `prettier`.

There are several rules in the [`eslint:recommended` ruleset](http://eslint.org/docs/rules/) that Kelsus style enforces in your project.

To see how the `kelsus` config compares with `eslint:recommended`, refer to the [source code of `index.js`](https://github.com/kelsus/eslint-config-kelsus/blob/master/index.js), which lists every ESLint rule along with whether (and how) it is enforced by the `kelsus` config.

### Create an `.eslintignore` config file.

```bash
touch .eslintignore
```

Content:

```bash
# /node_modules/* and /bower_components/* ignored by default

# Ignore built files except build/index.js
build/*
publish/*
!build/index.js

# Ignore the shared folder because is used with docker-compose, no need of linting
/shared/*

# Ignore the deploy folder because is used for deploy, no need of linting
/deploy/*

# Ignore the dosc folder because is used for documentation files, no need of linting
/docs/*
```

# PRETTIER

On Kelsus, we use [Prettier](https://prettier.io) as source for Opinionated Code Formatting.

> `kelsus` ESLint configuration already extends `prettier` that will turns off all rules that are unnecessary or might conflict with Prettier.

## Installation

```js
yarn add --dev prettier eslint-config-prettier eslint-plugin-prettier
```

## Setup config.

Add `prettier` configuration to the `package.json`.

```js
{
  "prettier": {
    "printWidth": 100,
    "singleQuote": true
  },
}
```

# SCRIPTS

## To run add scripts to your `package.json`

```json
"scripts": {
  "format-output": "prettier '**/*.{js,jsx}'",
  "format": "prettier --write '**/*.{js,jsx}'",
  "lint-errors": "eslint '**/*.{js,jsx}' --quiet",
  "lint": "eslint '**/*.{js,jsx}'",
}
```

* "format-output": This will show on the screen the format changes in your code that will be
  made if you run `prettier`.
* "format": This will format your code with `prettier`.
* "lint": This script will report errors and warnings of your code, based on the eslint-rules of your configuration.
* "lint-errors": This script will report only errors of your code, based on the eslint-rules of your configuration.

# TOOLS

## Install & Configure Visual Studio's Extensions

1. Install Prettier extention in Visual Studio -
   [JavaScript formatter by Esben Petersen](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
2. Install the ESLint extention in Visual Studio -
   [ESLint by Dirk Baeumer](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
3. Add a shortcut to make eslint fix all auto-fixable problems. Add this to your
   keybindings.json

   ```json
   [
     {
       "key": "ctrl+l",
       "command": "eslint.executeAutofix",
       "when": "editorTextFocus && !editorReadonly"
     }
   ]
   ```

   ##

   ## License

Apache-2 © Kelsus
