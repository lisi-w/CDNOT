Contribute to ESGF Documentation
================================

This page will explain how to contribute to these docs and add your own pages.

Clone CDNOT Repository
----------------------

First, clone our repository::

    git clone https://github.com/lisi-w/CDNOT.git

You should see a list of helpful scripts and our ``docs`` directory.

Conda Environment
-----------------

In order for the scripts to convert the markdown files for this documentation site, you should have a conda environment with ``m2r`` installed, a program which converts markdown to restructured text::

    conda create -n docs
    conda activate docs
    conda install pip
    pip install m2r

Alternatively, you can use pip to install ``m2r``::

    pip install m2r

If you opt for this method, you will need to edit the ``update-repo.sh`` script to remove the conda activation line. Alternatively, if your conda env is not named docs, please change the ``ENV`` variable at the top of the ``update-repo.sh`` script.


Add a New Repository
--------------------

To add a new file or multiple files from a repository which we do not pull from, use the ``add-repo.sh`` script like so::

    bash add-repo.sh <repository_url> <filename>

Where ``<repository_url>`` is the full link ending in .git that we can use to clone the repo, and ``<filename>`` is the optional filename to specify.
If you do not specify a file, all files in the repository's docs directory will be converted and added.
NOTE: this script requires that the repository has a subdirectory named docs and that the file specified or all files inside the docs directory are in the markdown format.

Add a New File From an Existing Repository
------------------------------------------

To add a new file from a repository which we already pull from, use the ``add-file.sh`` script like so::

    bash add-file.sh <repo_title> <filename>

Where ``<repo_title>`` is the name of the repository (e.g., for this repository, CDNOT), and ``<filename>`` is the name of the file you wish to add.
As above, the file must be in markdown format.

You can then manually push your changes to your branch or you can fork the repository instead and push there, and make a pull request. We will then review your additions.

Variables
---------

In order to run the above scripts, please clone both of the repositories below and place them in a directory together. The path to this directory is assumed to be ``~/docs-repos``.
If your path is different from this, please edit each of the scripts to reflect this by changing the ``REPODIR`` variable.

Additionally, the scripts assume that this repository is stored in ``~/cdnot``, so if it is not, please edit each of the scripts to reflect this by changing the ``BASEDIR`` variable.


Repositories We Currently Pull From
-----------------------------------

So that you know which script to use, we have included a list here of repositories we currently pull from:

 * `esgf-docker <https://github.com/ESGF/esgf-docker/>`_
 * `esgf.github.io <https://github.com/watucker/esgf.github.io/>`_


