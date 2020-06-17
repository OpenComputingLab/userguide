---
jupyter:
  jupytext:
    notebook_metadata_filter: rise
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.2'
      jupytext_version: 1.4.2
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
  rise:
    enable_chalkboard: true
    scroll: true
---

### Running An Open Computing Lab Environment On Your Own Computer Using `repo2docker`

You can run an *Open Computing Lab* environment on your computer by building it from scratch using `repo2docker`.

To use `repo2docker` you will need to install Docker and the `jupyter-repo2docker` Python package.

- install Docker from the Docker website;
- in a terminal / from a command prompt, run `python3 -m pip install --upgrade jupyter-repo2docker`

With Docker and `jupyter-repo2docker` installed, you can create an Open Computing Lab environment image by running a command of the form:

`jupyter-repo2docker \
    --no-run \
    --user-name=jovyan \
    --image=YOUR-IMAGE-REFERENCE \
    OPEN_COMPUTING_LAB_GITHUB_REPO_URL`
    
where:

- `YOUR-IMAGE-REFERENCE` might be something like `ou-software/COURSECODE`; and
-  `OPEN_COMPUTING_LAB_GITHUB_REPO_URL` might be something like `https://github.com/ouseful-course-containers/ou-example`.

Once the image is built, you can run it using a command of the form:

`docker run --name myContainerName -p 8NNN:8888 -v "$PWD:/home/jovyan/work" -e JUPYTER_TOKEN="letmein"
YOUR-IMAGE-REFERENCE`

where `NNN` might meaningfully be the three digits of from the relevant course code. *(The quotes round the volume mount cope with spaces in the `$PWD` directory path.)*

For example, for a `TM129` image, you might run the commands:

`jupyter-repo2docker \
    --no-run \
    --user-name=jovyan \
    --image=tm129ou \
    https://github.com/innovationOUtside/tm129-robotics2020`

and then:

`docker run --name tm129work -p 8129:8888 -v $PWD:/home/jovyan/work -e JUPYTER_TOKEN="letmein"
tm129ou`

*For more details regarding running Open Computing Lab environments using Docker containers, including mirroring files between your desktop and the container, see the guidance documents __using _docker.md__ and __obtaining_materials.md__.*

*For a full list of Open Computing Lab images, see: https://github.com/OpenComputingLab/environments .*