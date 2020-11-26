# poetry-setup-multi-platform

Install poetry on multiple platforms and add path

## useit

```yml
on:
  push:
  pull_request:
jobs:
  ci:
    runs-on: ${{ matrix.os }}
    strategy:
      matrix:
        os:
          - macos-11.0
          - macos-latest
          - windows-latest
          - ubuntu-20.04
          - ubuntu-latest
          - ubuntu-16.04
        python-version: [2.7, 3.6, 3.8, 3.9]
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-python@v2
        with:
          python-version: ${{ matrix.python-version }}
      - uses: atu4403/poetry-setup-multi-platform@v1
      - run: poetry --version
        shell: bash
```

## License

MIT © [atu4403](https://github.com/atu4403)
