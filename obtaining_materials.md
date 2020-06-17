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

### Obtaining a Module's Instructional Materials

Different course modules may use different approaches for distributing instructional materials for use in the Open Computing Lab environment associated with a particular course.

The main approaches are:

- providing instructional materials and activity resources in one or more zipped files on the VLE;
- providing instructional materials and activity resources in a Github repository of their own;
- providing instructional materials and activity resources packaged inside the *Open Computing Lab* container.

### Downloaded Files

If materials are distributed via file downloads, for example, zipped file archives, you can get the files into the *Open Computing Lab* environment in a variety of ways depending on where you are running the environment:

#### From any notebook server

You can upload files via any notebook server homepage. Simply click on the upload button and select the file you want to upload:

![](../images/jupyter_upload.png)

If you upload a `.zip` file, you will need to unzip it.

From the notebook homepage `Open` menu, open a new terminal.

Optionally, enter the command `ls` and hit return to list the files in the current directory and check the file name. To unzip your uploaded file, for example `upload.zip`, run the command:

`unzip upload.zip`


### Extracting Files Distributed As Part of an Open Computing Lab Container Onto Your Desktop

Some *Open Computing Lab* environments may contain instructional materials and resources pre-packaged inside the container. Whilst you can work with these resources in the OCL environment, they will not be shared onto tyour computer desktop.

Typically, such resources will be located inside the `content` directory (if they are in another location, the module documentation or OCL documentation for that environment should say where). On the notebook homepage, check to select the `content` directory (or whatever the name of the distributed content folder is) and then click `Rename` in the toolbar. Rename the folder as `notebooks/distributed`. You should then see the content of the `content` folder originally just inside the container has now been copied into the `distributed` directory inside your working directory.

These files now exist on your computer, even if the Docker container is stopped or deleted; they will also be available inside the *Open Computing Environment* container.


### Files in a Github Repository

If files are distributed via a Github repository, you can download the files as `.zip` archive file from the repository homeage and then upload them to your notebook enviornment.

The contents of a repository can also be loaded into a notebook environment using the `nbgitpuller` application. 

For example, suppose you want to import content from a repository `https://github.com/ORGANISATION/REPOSITORY` such as `https://github.com/innovationOUtside/tm129-robotics2020` where the `ORGANISATION` is `innovationOUtside` and the `REPOSITORY` is `tm129-robotics2020`.

From your notebook homepage, for example at `http://localhost:8129/tree` (your port number may well be different to `8129`...) change the path from `tree` to:

`git-pull?repo=https%3A%2F%2Fgithub.com%2FORGANISATION%2FREPOSITORY&urlpath=tree%2FREPOSITORY%2F&depth=1`
 
to give a URL of the form:

`http://localhost:YOUR_PORT_NUMBER/git-pull?repo=https%3A%2F%2Fgithub.com%2FORGANISATION%2FREPOSITORY&urlpath=tree%2FREPOSITORY%2F&depth=1`

Entering this URL will download the contents of the repository, making them available via the notebook server homepage and saving them to you local, shared directory if you are working with a local, shared workspace.
