# Singularity Anaconda: The Most Popular Python Data Science Platform

Singularity image for [Anaconda 5.3.0](https://www.anaconda.com).

## Build

You can build a local Singularity image named `anaconda3.5.3.0.simg` with:

```
$ sudo singularity build anaconda3.5.3.0.simg Singularity
```

## ~~Deploy~~

TODO

## Usage

Help

```console
$ singularity help anaconda3.5.3.0.simg


  anaconda 5.3.0
  ---------------------------
  ipython version: 6.5.0
  python version: 3.7.0
  conda version: 4.5.11
  anaconda CLI version: 1.7.2

  Usage:
  $ singularity run --app ipython anaconda3-anaconda3-latest.simg [args]
  $ singularity run --app python anaconda3-anaconda3-latest.simg [args]
  $ singularity run --app conda anaconda3-anaconda3-latest.simg [args]
  $ singularity run --app anaconda anaconda3-anaconda3-latest.simg [args]
  $ singularity shell anaconda3-anaconda3-latest.simg
```

## Run

### ipython

The `ipython` command will land the user in an ipython shell

```console
$ singularity run --app ipython anaconda3.5.3.0.simg
Python 3.7.0 (default, Jun 28 2018, 13:15:42)
Type 'copyright', 'credits' or 'license' for more information
IPython 6.5.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]:
```

### python

The `python` command will land the user in an python shell

```console
$ singularity run --app python anaconda3.5.3.0.simg
Python 3.7.0 (default, Jun 28 2018, 13:15:42)
[GCC 7.2.0] :: Anaconda, Inc. on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

### conda

```console
$ singularity run --app conda anaconda3.5.3.0.simg --help
usage: conda [-h] [-V] command ...

conda is a tool for managing and deploying applications, environments and packages.

Options:

positional arguments:
  command
    clean        Remove unused packages and caches.
    config       Modify configuration values in .condarc. This is modeled
                 after the git config command. Writes to the user .condarc
                 file (/home/cc/.condarc) by default.
    create       Create a new conda environment from a list of specified
                 packages.
    help         Displays a list of available conda commands and their help
                 strings.
    info         Display information about current conda install.
    install      Installs a list of packages into a specified conda
                 environment.
    list         List linked packages in a conda environment.
    package      Low-level conda package utility. (EXPERIMENTAL)
    remove       Remove a list of packages from a specified conda environment.
    uninstall    Alias for conda remove. See conda remove --help.
    search       Search for packages and display associated information. The
                 input is a MatchSpec, a query language for conda packages.
                 See examples below.
    update       Updates conda packages to the latest compatible version. This
                 command accepts a list of package names and updates them to
                 the latest versions that are compatible with all other
                 packages in the environment. Conda attempts to install the
                 newest versions of the requested packages. To accomplish
                 this, it may update some packages that are already installed,
                 or install additional packages. To prevent existing packages
                 from updating, use the --no-update-deps option. This may
                 force conda to install older versions of the requested
                 packages, and it does not prevent additional dependency
                 packages from being installed. If you wish to skip dependency
                 checking altogether, use the '--force' option. This may
                 result in an environment with incompatible packages, so this
                 option must be used with great caution.
    upgrade      Alias for conda update. See conda update --help.

optional arguments:
  -h, --help     Show this help message and exit.
  -V, --version  Show the conda version number and exit.

conda commands available from other packages:
  build
  convert
  develop
  env
  index
  inspect
  metapackage
  render
  server
  skeleton
```

### anaconda

```console
$ singularity run --app anaconda anaconda3.5.3.0.simg --help
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
$ singularity shell anaconda3.5.3.0.simg
Singularity: Invoking an interactive shell within container...

Singularity anaconda3.5.3.0.simg:~/singularity-dev-images/anaconda3> python -V
Python 3.7.0
Singularity anaconda3.5.3.0.simg:~/singularity-dev-images/anaconda3> ipython -V
6.5.0
Singularity anaconda3.5.3.0.simg:~/singularity-dev-images/anaconda3> conda -V
conda 4.5.11
Singularity anaconda3.5.3.0.simg:~/singularity-dev-images/anaconda3> anaconda -V
anaconda Command line client (version 1.7.2)
```
