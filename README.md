:
Provides `pyenv all` so that you can run the same code under all of the python versions you have installed.

Installation
============

Just git clone this repository into a new subdirectory of your pyenv plugins directory:

```
git clone https://github.com/claco/pyenv-all ~/.pyenv/plugins/pyenv-all
```

Usage
=====

Just `pyenv all <code you want to run>`. For example to run pip against all python versions that you have installed, use:

```
$ pyenv all pip install -r requirements.txt
```

By default pyenv all will output a little notification explaining what it is doing for each python:

```
$ pyenv all python --version
2.7.10>> python --version
Python 2.7.10

2.7.11>> python --version
Python 2.7.11
```

To suppress this, pass --bare

```
$ pyenv all --bare python --version
Python 2.7.10

Python 2.7.11
```

By default pyenv all will stop on the first failure.

```
$ pyenv all python --vresion
2.7.10>> python --vresion
Unknown option: --
usage: python [option] ... [-c cmd | -m mod | file | -] [arg] ...
Try 'python -h' for more information.
```

To suppress this, pass --force

```
$ pyenv all --force python --vresion
2.7.10>> python --vresion
Unknown option: --
usage: python [option] ... [-c cmd | -m mod | file | -] [arg] ...
Try 'python -h' for more information.

2.7.11>> python --vresion
Unknown option: --
usage: python [option] ... [-c cmd | -m mod | file | -] [arg] ...
Try 'python -h' for more information.
```

Credit
======

This is a fork from the rbenv version of the all command by [Conrad Irwin](https://github.com/ConradIrwin/rbenv-all)
