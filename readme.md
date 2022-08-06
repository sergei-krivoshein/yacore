# yacore
[![Github actions status for master branch](https://github.com/pohmelie/yacore/actions/workflows/ci.yml/badge.svg?branch=master)](https://github.com/pohmelie/yacore/actions)
[![Codecov coverage for master branch](https://codecov.io/gh/pohmelie/yacore/branch/master/graph/badge.svg)](https://codecov.io/gh/pohmelie/yacore)
[![Pypi version](https://img.shields.io/pypi/v/yacore.svg)](https://pypi.org/project/yacore/)
[![Pypi downloads count](https://img.shields.io/pypi/dm/yacore)](https://pypi.org/project/yacore/)

**Y**et **A**nother **CORE** library

## Reason
- Reduce daily routine to start new service.
- Reduce errors on copy/paste things from previous projects.

## Features
- Build on top of [`facet`](https://github.com/pohmelie/facet), [`cock`](https://github.com/pohmelie/cock) and [`giveme`](https://github.com/steinitzu/giveme). This means **services**, **configuration** and **dependency injection**.
- Flexible installation (install only what you need for current service, e.g. `pip install yacore[db-postgresql,net-http]`)
- Couple backends for databases, logging, networking and whatever in strict service-like style.

## Current implementation matrix
|database|logging|network|executors|
|-|-|-|-|
|postgres|stdlib|httpx + fastapi + hypercorn|thread pool executor
||loguru|||

## Requirements
- python 3.9+

## Usage
You can start new project from scratch with cookiecutter template via:
```
cookiecutter gh:pohmelie/cookiecutter-yacore
```
Read more at [cookiecutter-yacore](https://github.com/pohmelie/cookiecutter-yacore).

# Documentation
TBD

# License
`yacore` is offered under MIT license.

# Development
## Run tests
Since coverage issue/feature, plugins coverage is broken by default. [Workaround](https://pytest-cov.readthedocs.io/en/latest/plugins.html):
``` bash
COV_CORE_SOURCE=yacore COV_CORE_CONFIG=.coveragerc COV_CORE_DATAFILE=.coverage.eager pytest
```