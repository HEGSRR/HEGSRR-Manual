# Reproduction

The whole concept behind open science is that other researchers or students will be able to reproduce, replicate, and extend scientific studies after they are published.
This chapter is devoted to that epilogue: how to engage with a published open science study.
The repurposing of a scientific study will normally start with reproducing the original study results-- a process that will differ depending on the computational environment and original materials.
We hope that by standardizing a research template, we will have eased the work of reproducing the study.

This chapter provides some guidance for reproducing a study that is specific to research published with an open science workflow and conforming to version 2.0 or greater of the [HEGSRR-Template](https://www.github.com/HEGSRR/HEGSRR-Template).
The chapter essentially outlines methods for reproducing the computational environment of a prior study.

## Our template

Our reproducibility template, which can be found at [HEGSRR/HEGSRR-Template](https://github.com/HEGSRR/HEGSRR-Template) on GitHub, is designed to reduce common frustrations when trying to execute a compendium for computational geography.
Here are some tips on recovering the computational environments recorded in packages using our template.

### R

R is "a free software environment for statistical computing and graphics".
To install R, navigate to <https://cloud.r-project.org/>.
Additionally, install RStudio (<https://posit.co/downloads/>), the most popular IDE for R. ^[Jetbrains, [The State of Developer Ecosystem in 2020](https://www.jetbrains.com/lp/devecosystem-2020/r/) survey]

Those looking for a "cloud" solution may want to try out [Posit Cloud](https://posit.cloud/).

#### The `groundhog` package

Our template ([HEGSRR/HEGSRR-Template](https://github.com/HEGSRR/HEGSRR-Template)) uses the package `groundhog` ([CredibilityLab/groundhog](https://github.com/CredibilityLab/groundhog)) to achieve reproducibility of R scripts.

Given a date and a list of packages needed, `groundhog` can retrieve the most up-to-date version of both R and these packages on that date.

To recover the list of packages, in the relevant `.Rmd` file, look for references to `groundhog`.
This is typically in a code chunk that deals with setup tasks.

As [recommended](https://groundhogr.com/using/) by `groundhog`'s developers, a sensible first step is to change the specified `groundhog.day` to a reasonably recent date - a date corresponding to your version of R, or a very recent date such as last week.

Then, we can execute the main function, `groundhog.library()`.
Depending on the date you selected, you may need to install another version of R that was up-to-date on that date.
This is expected, because changes in R itself may impact computational results as well.
You may also need to give `groundhog` permission to install its packages to a certain folder; for our template, this has been set to `data/scratch/groundhog/`.

If the code functions as expected, then you are all set!
If not, then we can amend the groundhog day back to the original one;
after installing the correct version of R, `groundhog` will proceed to install the packages on that date.

See the article [Changing R version for the RStudio Desktop IDE](https://support.posit.co/hc/en-us/articles/200486138-Changing-R-versions-for-the-RStudio-Desktop-IDE) for how to tell RStudio to use a specific version of R.

### Python

Installing Python locally can be somewhat complicated.
In addition to Python, [Jupyter](https://jupyter.org/) is also needed to have interactive notebooks.
Tutorials found on the Internet also frequently mention [conda](https://docs.conda.io/en/latest/), a package manager; [additional packages](https://stackoverflow.com/a/43197286) such as `ipykernel` or `nb_conda_kernels` may also be needed.

As an alternative, [many platforms](https://datasciencenotebook.org/) offer a "cloud" notebook that requires minimal setup.
Additional benefits of these cloud notebooks *may* include:

- Disposable environment (see the [Disposable environment](#disposable-environment>) section below)
- No hardware requirement for the user
- Access to premium hardware for more computational power, usually at a cost
- Share and collaborate with others

#### The `pigar` package

For Python, our template ([HEGSRR/HEGSRR-Template](https://github.com/HEGSRR/HEGSRR-Template)) uses the package `pigar` ([damnever/pigar](https://github.com/damnever/pigar)) to generate a list of packages needed.

The generated list is named `requirements.txt`, and can be found under `procedure/environment/`.

#### Disposable environment
Installing packages, even from `pip`, can make your system environment messy.

Fortunately, disposable environments are available so that one does not have to worry about leaving a messy system behind.
One example is [Google Colab](https://colab.google/), where one is given a fresh machine whenever one connects to a Jupyter runtime.

If you are using such an environment, then simply run the following code (in Jupyter) to install the required packages:

```python
!pip install -r /path/to/requirements.txt
```

#### Package management
However, if you are working on a personal laptop, departmental machine, or another non-disposable environment, then keeping the system tidy is desirable.

In this case, before installing all the packages listed inside `requirements.txt`, a "virtual environment" should be created.
With a virtual environment, no changes are made at the system-level.
Python's own [venv](https://docs.python.org/3/library/venv.html) and [conda](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) are two common approaches.

Here is a tutorial from the website RealPython that walks you through using, as well as motivates, venv: [Python Virtual Environments: A Primer](https://realpython.com/python-virtual-environments-a-primer/)

## Other compendiums

Here are some general tips for how to recover from a research compendium one might find on the Internet.

### R

If you encounter a list of packages and their respective versions, you will have to install an old version manually.
You can do this with the `remotes::install_version()` function documented [here](https://search.r-project.org/CRAN/refmans/remotes/html/install_version.html).

However, older version of packages on CRAN are usually only available in "source" form, and not an immediately usable "binary" form.
This means that you will need to have an R development environment installed.
You can check if you do by running `devtools::has_devel()`.

On Windows, the "development environment" is [RTools](https://cran.r-project.org/bin/windows/Rtools/);
on MacOS [the process](https://mac.r-project.org/tools/) is slightly more complicated.

One further complication is that packages often require system-level dependencies.
These dependencies are additional software that are not always available, or consistent, across different machines.
Thus, installing "source" packages is often prone to failure.

#### The `renv` package

Analogous to `venv` in Python, `renv` records the versions of R and its packages for a certain project, and isolates these packages in a separate virtual environment.

Per [the documentation](https://rstudio.github.io/renv/articles/renv.html#collaboration), a project with `renv` will contain a `renv` directory, as well as a `renv.lock` file.
By opening the project, `renv` will automatically activate itself and prompt you to run `renv::restore()`, which restores the virtual environment.

Note that `renv` usually has to install from "source" when recovering, so this will often fail.
See `renv`'s [Caveats page](https://rstudio.github.io/renv/articles/renv.html#caveats) for details.

### Python

Projects using virtual environments (`venv`, `virtualenv`, `conda`, Poetry, etc.) will usually at least mention the method used.
One can also look for hints in the folder structure, for example a `venv` folder.
Once the particluar solution is located, the documentation for restoring that environment can then be readily found online.

#### Manually create `requirements.txt`

If you encounter a list of package names in Python, it is possible to convert that list into a reproducible `requirements.txt` file.
Simply find a package version that works, and record it into the requirements file.

[Here is an example](https://pip.pypa.io/en/stable/reference/requirements-file-format/) requirements file.

Using the package `scipy` as an example:

- `scipy`: install [the latest version](https://pypi.org/project/scipy/) from the Python Package Index (PyPI).
- `scipy == 1.9.1`: install version 1.9.1 from PyPI.
- `scipy == 1.9.*`: install the latest version that starts with 1.9.1. This installs 1.9.3, unless `scipy` decides to release version 1.9.4.

To ensure repeatability, it is best practice to specify an exact version of packages; this is called "version pinning".

### Docker

If you encounter a compedium in the form of a Docker container or Dockerfile, you will need to run Docker.

Installing Docker (Desktop) on [Windows](https://docs.docker.com/desktop/install/windows-install/) or [MacOS](https://docs.docker.com/desktop/install/mac-install/) is possible, but complications and caveats exist.
The preferred way to use Docker (Server) is through a server running [a supported Linux distribution](https://docs.docker.com/engine/install/#server).

A Dockerfile contains instructions on how to create ("build") a Docker container; run [docker build](https://docs.docker.com/engine/reference/commandline/build/) to turn a project-with-Dockerfile into a container.
Alternatively, the Docker container may have already been built; in this case, [docker pull](https://docs.docker.com/engine/reference/commandline/pull/) the container onto your machine.
Once we have a container, we can use [docker run](https://docs.docker.com/engine/reference/commandline/run/) to execute the container.

Note that Docker images are essentially virtual machines inside your system, so you may not be able to directly communicate with the virtual machine. 
Often the communication happens through a browser.
For example, the Docker image can run RStudio Server (or JupyterLab), and you can access the service with a browser.

#### Cloud services

Alternatively, you can utilize an online service to run Docker.

Many platforms offer "virtual machines" that run Linux distributions, so you can install and run Docker inside these machines.
Another commonly-seen approach is for the platform to run Docker for you.

When using cloud services, especially "virtual machines", it is important to note that there is an increased risk of someone hacking into your cloud machine.
Therefore, when using a cloud service, it is desirable to follow common best practices, and take extra precautions to guard against unauthorized access to your machine.

## Acknowledgement

Special thanks to Yifei Luo for contributions to this chapter.
