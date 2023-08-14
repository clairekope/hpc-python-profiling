# High Performance Python - Course Preparation

This course will use GitLab Classroom and Jupyter Notebooks for delivering instructional materials. 
We'll also want to run Python on the HPCC instead of on your personal computer.

This means there are a couple of things you need to make sure you have set up ahead of our first class period.

## Accessing the HPCC

ICER's documentation offers several options for [accessing the HPCC](https://docs.icer.msu.edu/accessHPCC_overview/).
Since we'll be using Jupyter Notebooks, I personally recommend using [OnDemand](https://docs.icer.msu.edu/Open_OnDemand/).
You can also use the terminal in OnDemand to setup your [Python environment](#setting-up-python-environment) and [cloning GitLab Classroom repositories](#cloning-gitlab-repositories).

OnDemand offers both the traditional Jupyter Notebook through the [Jupyter Notebook Interactive App](https://ondemand.hpcc.msu.edu/pun/sys/dashboard/batch_connect/sys/bc_icer_jupyter/session_contexts/new) as well as the newer [JupyterLab](https://jupyter.org/try-jupyter/lab/?path=notebooks%2FIntro.ipynb) interface through the [Jupyter (beta) Interactive App](https://ondemand.hpcc.msu.edu/pun/sys/dashboard/batch_connect/sys/bc_icer_jupyter_beta/session_contexts/new). I personally recommend JupyterLab because it offers a Table of Contents for easier navigation inside Notebooks!

<u>Optionally, if you prefer to run Jupyter Notebooks through VSCode, you can follow this guide from ICER.</u>

## Cloning GitLab Repositories

If you're reading this README, you've already successfully navigated GitHub Classroom.
Now, clone this repository **to the HPCC.**

## Setting Up Python Environment

I recommend using the [Conda package manager](https://docs.conda.io/en/latest/) to manage your Python environment for this course. Conda is installed alongside the [Anaconda](https://www.anaconda.com/), [Miniconda](https://docs.conda.io/en/latest/miniconda.html), and [Mambaforge](https://github.com/conda-forge/miniforge#mambaforge) Python distributions.

As part of this repository, I have included a `.yml` file compatible with Conda that will install the necessary packages into a *separate environment*. This way, if you already use Conda to manage Python for your research on the HPCC, this course will not interfere.

Installing a Conda-based distribution (such as Anaconda) on the HPCC is slightly different than installing it on your personal computer. **Please install Conda following [ICER's guide](docs.icer.msu.edu/Using_conda/).**

With the `Conda/3` module loaded following the ICER Conda guide, run 
```
conda env create -f hp-python.yml
```

To use this environment, run `conda activate hp-python` on the command line or specify the environment name `hp-python` when requesting an OnDemand job. You may need to check the "Launch Jupyter Notebook using the Anaconda installation in my home directory" box in OnDemand.

## Reading for Day 1

These brief readings will familiarize you with concepts needed for in-class activities on Day 1.

- [IPython/Jupyter Magic Commands]
- [Profiling and Timing Magic Commands](https://jakevdp.github.io/PythonDataScienceHandbook/01.07-timing-and-profiling.html)
- [Python Operator Precedence](https://introcs.cs.princeton.edu/python/appendix_precedence/)