# cf

[![Build Status](https://github.com/hoffa/cf/workflows/.github/workflows/workflow.yml/badge.svg)](https://github.com/hoffa/cf/actions)

Tiny convenience script for easily checking formatting with `clang-format`.

Will run on pretty much any POSIX system.

## Installation

```shell
curl -Lo /usr/local/bin/cf https://raw.githubusercontent.com/hoffa/cf/master/cf
chmod +x /usr/local/bin/cf
```

## Usage

```shell
cf
```

All arguments are passed as environment variables.

Files matching `INCLUDE` are included. Those matching `EXCLUDE` are excluded. Both are passed to `grep -E`.

Use `FORMAT=1` to format the files instead of checking for differences.

### In CI

For example:

```shell
curl -L https://raw.githubusercontent.com/hoffa/cf/master/cf | DIR=src EXCLUDE="json\.hpp" sh
```

If any of the files differ, `cf` will exit with a non-zero code.
