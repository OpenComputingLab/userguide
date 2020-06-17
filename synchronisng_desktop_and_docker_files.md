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

### Synchronising Desktop and Docker Files

Docker containers are self-contained virtual machines, running their own file system within the container.

If you are running a Docker container using Docker on your own computer, you can share files between the Docker container and your desktop. This means that files will exist on your desktop and be available to you even if the Docker container is switched off or destroyed.

Desktop directories (folders) and their subdirectories are "mounted' into the container using the `-v` parameter when starting a Docker continer. You can use the `-v` argument mutliple times to mount multiple different directories / folders onto different directories inside the container.

*See also:*

- for how to save your files see: `saving_and_checkpointing_your_work.md`;
- the *Extracting Files Distributed As Part of an Open Computing Lab Container Onto Your Desktop* section of `using_docker.md`.
