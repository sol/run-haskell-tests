```yaml
name: build

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ${{ matrix.os }}

    strategy:
      matrix:
        os:
          - ubuntu-latest
          - macos-latest
          - windows-latest

    steps:
      - uses: actions/checkout@v4
      - uses: sol/run-haskell-tests@v2
```
