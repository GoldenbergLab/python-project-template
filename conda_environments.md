# Conda environments for reproducibility

We use Anaconda (henceforth called *conda*) to manage package versions used for code you publish. In addition to your code, you will publish a file specifying a conda *environment*, which specifies which packages and versions you used, and how they can be accessed, ensuring version conflicts aren't an issue.

**If you're familiar with conda already, then you can skip this guide -- just make a conda environment that covers the dependencies of the project, and include the .yml file in your repo for readers to use.**

**If you're less comfortable using the terminal to set up conda, and would prefer remaining in the Jupyter interface, use the notebooks in `conda_notebooks` as a guide to run the following commands. The following guide will still likely be helpful :)**

## 0. Why use a conda environment?

As you're probably aware, code in Python and R depends on importing a lot of packages, and these packages are constantly being updated. Unfortunately, this means that [a lot of published scientific code doesn't run correctly](https://datacolada.org/100)! 

To address this, we use conda, which allows you to run your code in an isolated *environment*, which you can have multiple of on the same machine, with only the packages/versions necessary for a single project. When you're finished with the project, you can export a description of this environment that allows people to run your code with the exact same package versions, on their own machines! Even if you aren't publishing code, environments also mean that you don't need to worry about conflicts between different projects on your computer.

## 1. Creating a conda environment
Before you start, you should have a version of conda installed on your machine. Everything in this guide can be done with the smaller Miniconda, but you can use "Anaconda distribution" for additional features. [See here for install instructions.](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html) (I'm not going to lengthen this guide with install info, and there are often complications like adding conda to PATH, but those are Googleable.) 

When you're done, you should be able to run `conda --help` from your terminal, and see a conda environment (by default: `base`) as part of your command prompt. 

**Creating a conda environment:**
To create a new conda environment, before you start a new project in Python, run the following line in terminal:

```bash
conda create --name <environment_name> python=<python version>
```
Specify the environment name (related to the project) and version of Python you want (most likely, you want the newest Python available, which at the time of writing is `python=3.13`. 

This will create a new environment with just the basic packages needed to run Python on your machine.  To see current conda environments on your machine. run `conda env list`. 

## 2. Using your conda environment

Now that you've made a conda environment, you should use it whenever you run Python code for that project. To enter/switch over to a conda environment, run:

```
conda activate <environment_name>
```
Once you do this, you'll notice the environment name show up in each new line of your command prompt. Now, when you run Python code, it will be run with the version of Python you've specified, and with any packages you've added.

### Installing conda packages
To install packages into your environment, you can either use `conda install` or `pip install`. **You should prefer conda install** if possible (short answer: conda does a better job managing interoperability). 

To install a package through conda, use [anaconda.org](https://anaconda.org/) to search for your package, and run the specified line. So, for example, if you want to install `pandas`, you could search and find [this page](https://anaconda.org/conda-forge/pandas), and run the provided install line:
```
conda install conda-forge::pandas
``` 
(Conda installs specify both a package and a *channel* that contains recipes for installing the package in a platform independent way. `conda-forge` will contain most of the basic packages you want!)

Unless you specify a version, conda will install your package in the most recent version compatible with your current packages and Python version. If the package you want isn't available from `conda install`, you can still use `pip install` within the conda environment.

***Note: If you're using Jupyter Notebook, you'll need to [install it](https://anaconda.org/conda-forge/notebook) in your new conda environment as well! Then run `jupyter notebook` from within the environment when you'd like.***

## 3. Exporting your conda environment
Once you'd like other people to be able to run your code, you can *export* your conda environment into a `.yml` file that describes how to reproduce your environment with the correct package versions. (You must do this at the end of your project for publication, but **if you're working with collaborators, do this often** so you're working on the same versions!)

All you need to do is run:
```
conda env export > environment.yml
```
(the filename can be whatever you want), and conda will write a description of your environment to that file.

(If you'd like to take an extra step to be platform-dependent, you can instead run `conda env export --from-history`, which will only include packages you explicitly installed, and none of the additional packages conda has added as dependencies. In this case, when your reader installs from this file, conda will have more flexibility to set up dependencies to support the same versions of the packages you actually care about.)

Then, simply include the file in your Github repo/wherever you're publishing code so people can use it. To install from this file, they will simply run `conda env create -f environment.yml`.

---
And that's it! For more info on using conda environments, including all of the commands shown above, [see this guide](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html).
 
