# sfm-action

GitHub Action for [sfm](https://github.com/toolsdotgo/sfm).

Currently just downloads either the latest or specified version and places it in the `$PATH` for subsequent steps to make use of. Future iterations may enable executing `sfm` directly from this Action.

## Usage

### Using the latest version of `sfm`

```yaml
name: Deploy my Stack

on: [push]

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Grab latest verison of sfm
        uses: toolsdotgo/sfm-action@v1

      - name: Form the Stack
        run: sfm mk -t ./my-stack.yml my-stack
```

### Using a specific version of `sfm`

```yaml
name: Deploy my Stack

on: [push]

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Grab latest verison of sfm
        uses: toolsdotgo/sfm-action@v1
        with:
          version: v1.1.0

      - name: Form the Stack
        run: sfm mk -t ./my-stack.yml my-stack
```
