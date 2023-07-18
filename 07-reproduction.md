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

### R

### Python

### Docker

## Acknowledgement

Special thanks to Yifei Luo for contributions to this chapter.
