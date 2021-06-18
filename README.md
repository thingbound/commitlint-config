# @thingbound/commitlint-config

Configuration for [Commitlint](https://commitlint.js.org/) for projects in
the @thingbound organization.

Follows [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
more or less exactly.

When using this config all commits will be on the form:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

## Using in projects

This config is used together with Commitlint as a [Husky](https://github.com/typicode/husky)
hook.

Install as dev dependencies:

```
$ npm install --save-dev @commitlint/cli husky @thingbound/commitlint-config
```

Create a file named `commitlint.config.js` and define that it to extend this
configuration:

```javascript
module.exports = {
  extends: [
    '@thingbound'
  ]
};
```

Then in `package.json` enable `commitlint` via Husky:

```json
{
  ...,
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
    }
  }
}
```
