# High Performance Python - Course Preparation

This course will use GitHab Classroom and Jupyter Notebooks for delivering instructional materials. 
We'll also want to run Python on the HPCC instead of on your personal computer.

This means there are a couple of things you need to make sure you have set up ahead of our first class period.

## Accessing the HPCC

ICER's documentation offers several options for [accessing the HPCC](https://docs.icer.msu.edu/accessHPCC_overview/).
Since we'll be using Jupyter Notebooks, I personally recommend using [OnDemand](https://docs.icer.msu.edu/Open_OnDemand/).
You can also use the terminal in OnDemand to setup your [Python environment](#setting-up-python-environment) and [cloning GitHub Classroom repositories](#cloning-githab-classroom-repositories).

OnDemand offers both the traditional Jupyter Notebook and the newer JupyterLab through the [Jupyter Interactive App](https://ondemand.hpcc.msu.edu/pun/sys/dashboard/batch_connect/sys/bc_icer_jupyter_ubuntu/session_contexts/new). I personally recommend JupyterLab because it offers a Table of Contents for easier navigation inside Notebooks! You can switch between traditional Notebooks and JupyterLab using the checkbox. The Python environment provided for this class already has both options installed.

Optionally, if you prefer to run Jupyter Notebooks through VSCode, you can follow [this guide](https://docs.icer.msu.edu/Jupyter_Notebook_in_VS_Code) from ICER.

## Cloning GitHub Classroom Repositories

If you're reading this README, you've already successfully accepted this assignment from GitHub Classroom.
Now, clone this repository **to the HPCC.** You'll need `hpc-python.yml` to set up your course Python environment in the [next step](#setting-up-python-environment).
The Notebook `workbook_profiling.ipynb` will be used **on the first day of class,** August 31, 2024.

GitHub offers a choice of URL to use when cloning a repository. The GitHub docs contain a [useful explanation of the different options](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls); I personally recommend either cloning with HTTPS or SSH. If you want to clone with HTTPS, you'll need to set up a [personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens) on GitHub. If you want to clone with SSH, you'll need to create an SSH key **on the HPCC** and upload it to GitHub. This option is more sophisticated and best done if you are already familiar with SSH keys; e.g., from using them to connect to the HPCC.

## Setting Up Python Environment

I recommend using the [Conda package manager](https://docs.conda.io/en/latest/) to manage your Python environment for this course. Conda is installed as part of the open source [Miniforge](https://github.com/conda-forge/miniforge) Python distribution. You may also be familiar with Conda from the Anaconda and Miniconda Python distributions; however, ICER now officially recommends the use of Miniforge. You can read more about [migrating an existing installation](https://docs.icer.msu.edu/Replacing_conda_install/) if you are interested.

You may also wish to experiment with [Mamba](https://mamba.readthedocs.io/en/latest/), a faster alternative to Conda. Mamba is best used with a fresh Miniforge installation.

Installing a Conda-based distribution on the HPCC is slightly different than installing it on your personal computer. **Please install Conda following [ICER's guide](docs.icer.msu.edu/Using_conda/).**

As part of this repository, I have included `hpc-python.yml`, a file compatible with Conda, that will install the necessary packages into a *separate environment*. This way, if you already use Conda to manage Python for your research on the HPCC, this course will not interfere.

Once Conda is installed, run the following to set up the course Python environment:
```
ssh dev-amd20-v100
module unload Python
module load Conda/3 CUDA/11.7.0
conda env create -f hpc-python.yml
```
If you opted to try Mamba, replace `conda` with `mamba` on the last line. 

**The installation will probably take a while!** 

Creating this environment *must* be done on the V100 development node, as this is the GPU will we use in the last part of class. If you install the environment on a node without a GPU, the GPU-related packages will not install correctly.

To use this environment while in the command line, run `conda activate hpc-python` on the command line. For OnDemand, you'll need to specify "Conda Environment" in the "Jupyter Location" dropdown and enter the path to your Conda environment in the "Conda Path" box; for example, `/mnt/home/kopenhaf/miniforge`.

## Course Teams Channel

Please access the Microsoft Teams [channel for this course](https://teams.microsoft.com/l/channel/19%3a3dd0be706c0e44b78efe9725782fce35%40thread.tacv2/High%2520Performance%2520Python?groupId=363209fc-9ec9-4541-af7d-820a23e72d62&tenantId=22177130-642f-41d9-9211-74237ad5687d). This channel is available for class-related discussion and will be used for general announcements.

## Pre-Class Survey

This class is open to students with a wide range of backgrounds and research goals. Please fill out this [pre-class survey](https://docs.google.com/forms/d/e/1FAIpQLSeuwv3JQioi-WoDjQ8_e2NbWzSa7Y6Eo6GrYjSA60AWjd8Mqw/viewform?usp=sf_link) so I can better adapt the material to your needs.

## Reading for Day 1

These brief readings will familiarize you with concepts needed for in-class activities on Day 1.

- [Profiling and Timing Magic Commands](https://jakevdp.github.io/PythonDataScienceHandbook/01.07-timing-and-profiling.html)
- [Python Operator Precedence](https://introcs.cs.princeton.edu/python/appendix_precedence/)