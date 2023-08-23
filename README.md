# High Performance Python - Course Preparation

This course will use GitHab Classroom and Jupyter Notebooks for delivering instructional materials. 
We'll also want to run Python on the HPCC instead of on your personal computer.

This means there are a couple of things you need to make sure you have set up ahead of our first class period.

## Accessing the HPCC

ICER's documentation offers several options for [accessing the HPCC](https://docs.icer.msu.edu/accessHPCC_overview/).
Since we'll be using Jupyter Notebooks, I personally recommend using [OnDemand](https://docs.icer.msu.edu/Open_OnDemand/).
You can also use the terminal in OnDemand to setup your [Python environment](#setting-up-python-environment) and [cloning GitHub Classroom repositories](#cloning-githab-classroom-repositories).

OnDemand offers both the traditional Jupyter Notebook through the [Jupyter Notebook Interactive App](https://ondemand.hpcc.msu.edu/pun/sys/dashboard/batch_connect/sys/bc_icer_jupyter/session_contexts/new) as well as the newer [JupyterLab](https://jupyter.org/try-jupyter/lab/?path=notebooks%2FIntro.ipynb) interface through the [Jupyter (beta) Interactive App](https://ondemand.hpcc.msu.edu/pun/sys/dashboard/batch_connect/sys/bc_icer_jupyter_beta/session_contexts/new). I personally recommend JupyterLab because it offers a Table of Contents for easier navigation inside Notebooks!

Optionally, if you prefer to run Jupyter Notebooks through VSCode, you can follow [this guide](https://docs.icer.msu.edu/Jupyter_Notebook_in_VS_Code) from ICER.

## Cloning GitHub Classroom Repositories

If you're reading this README, you've already successfully accepted this assignment from GitHub Classroom.
Now, clone this repository **to the HPCC.** You'll need `hp-python.yml` to set up your course Python environment in the [next step](#setting-up-python-environment).
The Notebook `workbook_profiling.ipynb` will be used **on the first day of class,** September 1, 2023.

## Setting Up Python Environment

I recommend using the [Conda package manager](https://docs.conda.io/en/latest/) to manage your Python environment for this course. Conda is installed alongside the [Anaconda](https://www.anaconda.com/), [Miniconda](https://docs.conda.io/en/latest/miniconda.html), and [Mambaforge](https://github.com/conda-forge/miniforge#mambaforge) Python distributions.

As part of this repository, I have included `hp-python.yml`, a file compatible with Conda, that will install the necessary packages into a *separate environment*. This way, if you already use Conda to manage Python for your research on the HPCC, this course will not interfere.

Installing a Conda-based distribution (such as Anaconda) on the HPCC is slightly different than installing it on your personal computer. **Please install Conda following [ICER's guide](docs.icer.msu.edu/Using_conda/).**

With the `Conda/3` module loaded following the ICER Conda guide, run 
```
conda env create -f hp-python.yml
```
It will probably take a while!

To use this environment, run `conda activate hp-python` on the command line or specify the environment name `hp-python` when requesting an OnDemand job. You may need to check the "Launch Jupyter Notebook using the Anaconda installation in my home directory" box in OnDemand.

## Course Teams Channel

Please access the Microsoft Teams [channel for this course](https://teams.microsoft.com/l/channel/19%3a3dd0be706c0e44b78efe9725782fce35%40thread.tacv2/High%2520Performance%2520Python?groupId=363209fc-9ec9-4541-af7d-820a23e72d62&tenantId=22177130-642f-41d9-9211-74237ad5687d). This channel is available for class-related discussion and will be used for general announcements.

## Pre-Class Survey

This class is open to students with a wide range of backgrounds and research goals. Please fill out this [pre-class survey](https://docs.google.com/forms/d/e/1FAIpQLSeuwv3JQioi-WoDjQ8_e2NbWzSa7Y6Eo6GrYjSA60AWjd8Mqw/viewform?usp=sf_link) so I can better adapt the material to your needs.

## Reading for Day 1

These brief readings will familiarize you with concepts needed for in-class activities on Day 1.

- [Profiling and Timing Magic Commands](https://jakevdp.github.io/PythonDataScienceHandbook/01.07-timing-and-profiling.html)
- [Python Operator Precedence](https://introcs.cs.princeton.edu/python/appendix_precedence/)