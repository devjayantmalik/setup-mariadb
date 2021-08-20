# setup-mariadb

The missing action for MariaDB :tada:

- Simpler than containers
- Works on Linux, Mac, and Windows
- Supports different versions

[![Build Status](https://github.com/devjayantmalik/setup-mariadb/workflows/build/badge.svg?branch=v1)](https://github.com/devjayantmalik/setup-mariadb/actions)

## Getting Started

Add it as a step to your workflow

```yml
- uses: devjayantmalik/setup-mariadb@v1
```

## Versions

Specify a version (defaults to the latest)

```yml
- uses: devjayantmalik/setup-mariadb@v1
  with:
    mariadb-version: 10.6
```

Currently supports

| Version        | `10.6` | `10.5` | `10.4` | `10.3` | `10.2` | `10.1` |
| -------------- | ------ | ------ | ------ | ------ | ------ | ------ |
| `ubuntu-20.04` |        | ✓      |        |        |        |
| `ubuntu-18.04` |        | ✓      | ✓      | ✓      | ✓      |
| `ubuntu-16.04` |        | ✓      | ✓      | ✓      | ✓      |
| `macos-11.0`   |        | ✓      | ✓      | ✓      | ✓      | ✓      |
| `macos-10.15`  |        | ✓      | ✓      | ✓      | ✓      | ✓      |
| `windows-2019` |        | ✓      | ✓      | ✓      | ✓      | ✓      |
| `windows-2016` |        | ✓      | ✓      | ✓      | ✓      | ✓      |

Test against multiple versions

```yml
strategy:
  matrix:
    mariadb-version: [10.6, 10.5, 10.4, 10.3, 10.2, 10.1]
steps:
  - uses: devjayantmalik/setup-mariadb@v1
    with:
      mariadb-version: ${{ matrix.mariadb-version }}
```

## Options

Create a database

```yml
- uses: devjayantmalik/setup-mariadb@v1
  with:
    mariadb-version: 10.6
    database: testdb
    username: test
    password: password
```

## Extra Steps

Run queries

```yml
- run: mysql -D testdb -e 'SELECT VERSION()'
```

## Option Defaults

| Option name     | Default  | Is Optional |
| --------------- | -------- | ----------- |
| mariadb-version | 10.5     | ✓           |
| database        | testdb   | ✓           |
| root-password   | password | ✓           |
| username        | test     | ✓           |
| password        | password | ✓           |

## Examples

- TODO: Will add it soon.

## Contributing

Everyone is encouraged to help improve this project. Here are a few ways you can help:

- [Report bugs](https://github.com/devjayantmalik/setup-mariadb/issues)
- Fix bugs and [submit pull requests](https://github.com/devjayantmalik/setup-mariadb/pulls)
- Write, clarify, or fix documentation
- Suggest or add new features
