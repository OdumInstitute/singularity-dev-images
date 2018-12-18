# Singularity Jupyter: Interactive Computing

Singularity image for [Jupyter 4.4.0](https://jupyter.org).

## Build

You can build a local Singularity image named `jupyter.4.4.0.simg` with:

```
$ sudo singularity build jupyter.4.4.0.simg Singularity
```

## ~~Deploy~~

TODO

## Usage

Help

```console
$ singularity help jupyter.4.4.0.simg


  Jupyter: Interactive Computing
  Version 4.4.0

  Usage:
  $ singularity run --app notebook \
    -B /run/user:/run/user \
    -B $(pwd):/opt/notebooks \
    jupyter-jupyter-latest.simg
  $ singularity run \
    -B /run/user:/run/user \
    -B $(pwd):/opt/notebooks \
    jupyter-jupyter-latest.simg [args]
```

Where:

- `-B /run/user:/run/user`: Allows the process to run from host space (required)
- `-B $(pwd):/opt/notebooks`: Volume mount (share) of user's present working directory as the location to save newly generated notebooks


## Run

### notebook

The `notebook` command is issued by the container and will spawn a new Jupyter notebook using the present working directory as the location to write new notebook objects to.

```bash
singularity run --app notebook \
  -B /run/user:/run/user \
  -B $(pwd):/opt/notebooks \
  jupyter.4.4.0.simg
```

Example

```console
$ singularity run --app notebook \
>   -B /run/user:/run/user \
>   -B $(pwd):/opt/notebooks \
>   jupyter.4.4.0.simg
Starting notebook...
Open browser to localhost:8888
[W 21:02:04.296 NotebookApp] WARNING: The notebook server is listening on all IP addresses and not using encryption. This is not recommended.
[W 21:02:04.296 NotebookApp] WARNING: The notebook server is listening on all IP addresses and not using authentication. This is highly insecure and not recommended.
[I 21:02:04.332 NotebookApp] JupyterLab extension loaded from /opt/conda/lib/python3.7/site-packages/jupyterlab
[I 21:02:04.332 NotebookApp] JupyterLab application directory is /opt/conda/share/jupyter/lab
[I 21:02:04.336 NotebookApp] Serving notebooks from local directory: /opt/notebooks
[I 21:02:04.336 NotebookApp] The Jupyter Notebook is running at:
[I 21:02:04.336 NotebookApp] http://(singularity-centos.novalocal or 127.0.0.1):8888/
[I 21:02:04.336 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
...
```

Navigate to the URL:PORT where your notebook is deployed at

<img width="80%" alt="Jupyter notebook" src="https://user-images.githubusercontent.com/5332509/50182887-83476400-02de-11e9-8f0f-5269fd82ac09.png">

Create a new notebook

<img width="80%" alt="Jupyter notebook" src="https://user-images.githubusercontent.com/5332509/50183347-d7067d00-02df-11e9-9c69-df615892b427.png">

Save your notebook

<img width="80%" alt="Jupyter notebook" src="https://user-images.githubusercontent.com/5332509/50183348-d7067d00-02df-11e9-8a96-411ffae7aaac.png">
