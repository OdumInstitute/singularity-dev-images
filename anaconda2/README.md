# Singularity Anaconda: The Most Popular Python Data Science Platform

Singularity image for [Anaconda 5.3.0](https://www.anaconda.com).

## Build

You can build a local Singularity image named `anaconda2.5.3.0.simg` with:

```
$ sudo singularity build anaconda2.5.3.0.simg Singularity
```

## Usage

Help

```console
$ singularity help anaconda2.5.3.0.simg


  anaconda 5.3.0
  ---------------------------
  ipython version: 5.8.0
  python version: 2.7.16
  conda version: 4.6.11
  anaconda CLI version: 1.7.2

  Usage:
  $ singularity run --app ipython anaconda2-anaconda2-latest.simg [args]
  $ singularity run --app python anaconda2-anaconda2-latest.simg [args]
  $ singularity run --app conda anaconda2-anaconda2-latest.simg [args]
  $ singularity run --app anaconda anaconda2-anaconda2-latest.simg [args]
  $ singularity shell anaconda2-anaconda2-latest.simg
```

## Run

### ipython

The `ipython` command will land the user in an ipython shell

```console
$ singularity run --app ipython anaconda2.5.3.0.simg
Python 2.7.16 |Anaconda, Inc.| (default, Mar 14 2019, 21:00:58)
Type "copyright", "credits" or "license" for more information.

IPython 5.8.0 -- An enhanced Interactive Python.
?         -> Introduction and overview of IPython's features.
%quickref -> Quick reference.
help      -> Python's own help system.
object?   -> Details about 'object', use 'object??' for extra details.

In [1]:
```

### python

The `python` command will land the user in an python shell

```console
$ singularity run --app python anaconda2.5.3.0.simg
Python 2.7.16 |Anaconda, Inc.| (default, Mar 14 2019, 21:00:58)
[GCC 7.3.0] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

### conda

```console
$ singularity run --app conda anaconda2.5.3.0.simg --help
usage: conda [-h] [-V] command ...

conda is a tool for managing and deploying applications, environments and packages.

Options:

positional arguments:
  command
    clean        Remove unused packages and caches.
    config       Modify configuration values in .condarc. This is modeled
                 after the git config command. Writes to the user .condarc
                 file (/home/stealey/.condarc) by default.
    create       Create a new conda environment from a list of specified
                 packages.
    help         Displays a list of available conda commands and their help
                 strings.
    info         Display information about current conda install.
    init         Initialize conda for shell interaction. [Experimental]
    install      Installs a list of packages into a specified conda
                 environment.
    list         List linked packages in a conda environment.
    package      Low-level conda package utility. (EXPERIMENTAL)
    remove       Remove a list of packages from a specified conda environment.
    uninstall    Alias for conda remove.
    run          Run an executable in a conda environment. [Experimental]
    search       Search for packages and display associated information. The
                 input is a MatchSpec, a query language for conda packages.
                 See examples below.
    update       Updates conda packages to the latest compatible version.
    upgrade      Alias for conda update.

optional arguments:
  -h, --help     Show this help message and exit.
  -V, --version  Show the conda version number and exit.

conda commands available from other packages:
  build
  convert
  debug
  develop
  env
  index
  inspect
  metapackage
  render
  server
  skeleton
  verify
```

### anaconda

```console
$ singularity run --app anaconda anaconda2.5.3.0.simg --help
WARNING: The conda.compat module is deprecated and will be removed in a future release.
usage: anaconda [-h] [--disable-ssl-warnings] [--show-traceback] [-v] [-q]
                [-V] [-t TOKEN] [-s SITE]
                ...

Anaconda repository command line manager

optional arguments:
  -h, --help            show this help message and exit
  -V, --version         show program's version number and exit

output:
  --disable-ssl-warnings
                        Disable SSL warnings (default: False)
  --show-traceback      Show the full traceback for chalmers user errors
                        (default: False)
  -v, --verbose         print debug information on the console
  -q, --quiet           Only show warnings or errors on the console

anaconda-client options:
  -t TOKEN, --token TOKEN
                        Authentication token to use. May be a token or a path
                        to a file containing a token
  -s SITE, --site SITE  select the anaconda-client site to use

Commands:

    auth                Manage Authorization Tokens
    label               Manage your Anaconda repository labels
    channel             [DEPRECATED in favor of label] Manage your Anaconda
                        repository channels
    config              Anaconda client configuration
    copy                Copy packages from one account to another
    download            Download notebooks from your Anaconda repository
    groups              Manage Groups
    login               Authenticate a user
    logout              Log out from your Anaconda repository
    move                Move packages between labels
    notebook            Interact with notebooks in your Anaconda repository
    package             Package utils
    remove              Remove an object from your Anaconda repository. Must
                        refer to the formal package name as it appears in the
                        URL of the package. Also use anaconda show <USERNAME>
                        to see list of package names. Example: anaconda remove
                        continuumio/empty-example-notebook
    search              Search in your Anaconda repository
    show                Show information about an object
    upload              Upload packages to your Anaconda repository
    whoami              Print the information of the current user
```

### shell

Invoke an interactive shell within the container

```console
$ singularity shell anaconda2.5.3.0.simg
Singularity: Invoking an interactive shell within container...

Singularity anaconda2.simg:~/singularity-dev-images/anaconda2> python -V
Python 2.7.16 :: Anaconda, Inc.
Singularity anaconda2.simg:~/singularity-dev-images/anaconda2> ipython -V
5.8.0
Singularity anaconda2.simg:~/singularity-dev-images/anaconda2> conda -V
conda 4.6.11
Singularity anaconda2.simg:~/singularity-dev-images/anaconda2> anaconda -V
WARNING: The conda.compat module is deprecated and will be removed in a future release.
anaconda Command line client (version 1.7.2)
Singularity anaconda2.simg:~/singularity-dev-images/anaconda2>
```
