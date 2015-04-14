# DataLad

DataLad aims to deliver a data distribution.  Original motive was to provide
a platform for harvesting data from online portals and
exposing collected data in a readily-usable form from [Git-annex]
repositories, while fetching data load from the original data providers.

# Status


It is currently in a "prototype" state, i.e. **a mess**. It is functional for
many use-cases but not widely used since its organization and configuration will
be a subject for a considerable reorganization and standardization.  Primary
purpose of the development is to catch major use-cases and try to address them
to get a better understanding of the ultimate specs and design.

## Code status:

* [![tests status](https://secure.travis-ci.org/datalad/datalad.png?branch=master)](https://travis-ci.org/datalad/datalad) travis-ci.org (master branch)

* [![Coverage Status](https://coveralls.io/repos/datalad/datalad/badge.png?branch=master)](https://coveralls.io/r/datalad/datalad)


# Tests

All tests are available under `datalad/tests`.  To exercise tests, the codebase
need to be "installed" to generate scripts for the entry points.  For that,
recommended course of action is to use virtualenv, e.g.

```sh
virtualenv --system-site-packages venv-tests
venv-tests/bin/pip install -r requirements
venv-tests/bin/python setup.py develop
```

and then use that virtual environment to run the tests, e.g. via

```sh
venv-tests/bin/python -m nose -s -v datalad
```

You can avoid entering venv-tests/bin  by simply activating that environment in
the current shell session:

```sh
source venv-tests/bin/activate
```

Some tests use testing repositories which are available as submodules
under the `datalad/tests/testrepos` submodule (two tier- to not pollute
top repository submodules namespace).  To enable those tests do

```sh
git submodule update --init --recursive
```

or clone with `--recursive` option originally.

# Dependencies

On Debian-based systems we recommend to enable
[NeuroDebian](http://neuro.debian.net) since we use it to provide
backports of recent fixed external modules we depend upon:

```sh
apt-get install patool python-bs4 python-git python-joblib git-annex
```

or otherwise you can use pip to install Python modules

```sh
pip install -r requirements.txt
```

and will need to install git-annex using appropriate for your OS means

# License

MIT/Expat

# Disclaimer

It is in a prototype stage -- **nothing** is set in stone yet -- but
already usable in a limited scope.

[Git-annex]: http://git-annex.branchable.com
