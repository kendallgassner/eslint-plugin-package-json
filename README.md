This repo is forked off of [eslint-plugin-package-json](https://github.com/zetlen/eslint-plugin-package-json) and is temporarily being used while https://github.com/zetlen/eslint-plugin-package-json/pull/11 is in the review process. The purpose of this published version is to have access to the `local-dependency` rule as it is being reviewed.

# @kendallgassner/eslint-plugin-package-json

Rules for valid, consistent, and readable package.json files

## Installation

You'll first need to install [ESLint](http://eslint.org):

```
$ npm i eslint --save-dev
```

Next, install `@kendallgassner/eslint-plugin-package-json`:

```
$ npm install @kendallgassner/eslint-plugin-package-json --save-dev
```

**Note:** If you installed ESLint globally (using the `-g` flag) then you must also install `eslint-plugin-package-json` globally.

## Usage

Add `package-json` to the plugins section of your `.eslintrc` configuration file. You can omit the `eslint-plugin-` prefix:

```json
{
    "plugins": ["@kendallgassner/eslint-plugin-package-json"]
}
```

```json
{
    "rules": {
        "@kendallgassner/package-json/local-dependency": 2
    }
}
```

## Supported Rules

-   [`package-json/order-properties`](docs/rules/order-properties.md): Require top-level properties to be in a conventional order (`"name"`first, etc.).
-   [`package-json/sort-collections`](docs/rules/sort-collections.md): Keep sub-collections like `"dependencies"` and `"scripts"` in alphabetical order.
-   [`package-json/valid-package-def`](docs/rules/valid-package-def): Validate `package.json` files against the NPM specification.
-   [`package-json/local-dependency`](docs/rules/local-dependency): Validates the casing for `file:` and `link:` dependencies in the `package.json` files. If the casing of these paths are incorrect yarn does not sub out the link when releasing.

These rules only run on `package.json` files; they will ignore all other files being linted. They lint `package.json` files at project root, and in any subfolder of the project, making this plugin great for monorepos.
