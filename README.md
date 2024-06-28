# NPM test action

The action is a [composite action](https://docs.github.com/en/actions/creating-actions/creating-a-composite-action)
that will run `npm ci` to install dependencies, and then `npm test` to run tests.

It makes use of:

* [actions/checkout](https://github.com/actions/checkout)
* [actions/setup-node](https://github.com/actions/setup-node)

# Usage

```yaml
- uses: wikiteq/npm-test-action@main
```

# Example

The below is an example of how to setup your GitHub Actions workflow on a repository:

`.github/workflows/main.yml`

```yaml
name: Example

on:
  push:
    branches: [ master ]
  pull_request:
    branches: [ "*" ]

jobs:
  npm-tests:
    name: NPM tests
    runs-on: ubuntu-latest
    steps:
      - uses: wikiteq/npm-test-action@main
```
