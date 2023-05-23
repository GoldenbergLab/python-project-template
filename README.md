# python-project-template

## How to use this template
This is a template for Python Projects in Goldenberg Lab. To use this template, please:

1. Download Anaconda and Python. We recommend starting with the latest Python version and Anaconda version. The tutorial [here](https://docs.jupyter.org/en/latest/install/notebook-classic.html) is helpful.
2. Create a virtual environment. To do this, open the anaconda prompt and use the command `conda create -n environment-name python=3.9 anaconda`. You may need a different version of Python depending on what packages you need to work with. After this, use the command `conda activate environnment-name` to activate the environment. We use virtual environments to manage our projects and packages in order to prevent conflicts of packages between projects. For example, if one project requires package version 3.2 and the other requires package version 3.3, it is impractical and messy to constantly uninstall and reinstall different versions of the same package. It makes much more sense to have two separate virtual enviornments, one for each project containing the corresponding version of the package.
4. Work on your project. Install any packages needed and begin coding. Keep in mind the organization process outlined below.
5. Organize your folders and files. We have provided a `processing` and `analysis` folder, but we recognize that your purposes for working in Python might be different. For example, if you have a Twitter data scraping project, you will want a separate Jupiter notebook or python script for each step of your data scraping project. The structure might look something like this:
    - 0 API scraping
    - 1 Data processing - cleaning, rows and columns
    - 2 Data processing - sentiment analysis 
    - 3 Data processing - merge sentiment with master data
6. When you are finished with your project, run `pip freeze > requirements.txt` in the top-level folder of your project. This will freeze all of the requirements that you used so the next person can easily replicate your work.
7. Update the command below for easy reproduction of your environment and packages. Change out `environment-name` for your environment and replace python version as needed. 

## Anaconda prompt commands for this project:
- `conda create -n environment-name python=3.9 anaconda`
- `conda activate environnment-name`
- `pip install -r requirements.txt` 


## Common commands for managing virtual environments

- `conda env list` shows all of your current virtual environments.
- `conda activate environment-name` activates the environment
- `conda deactivate` allows you to exit the virtual environment
