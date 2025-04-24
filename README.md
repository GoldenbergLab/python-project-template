# Template for Python Projects 
This is a template for Python Projects in the Goldenberg Lab. There are three folders: 

- **data** All of the data stored in this repo should be located in this folder. There are subfolders for raw data and processed data.
- **processing** All of the code designed for processing should be saved in this folder. 
- **analysis** should be used for analysis of processed data. 

Your workflow should be to:
- Place raw data in `data/raw`. **Use `.gitignore` to exclude all data, raw and processed, from Github! You should never upload any remotely sensitive data on Github.**
- Write and run code in `processing` that takes in this raw data, does all necessary cleaning, combining, and processing, and writes processed data file(s) to `data/processed`. Again, this file should be ignored by Git.
- Conduct your analysis, ideally in a Jupyter notebook, in `analysis`, reading in the processed data file. Visualizations should go in `analysis/img`, if you'd like to store them in the Github repo. (You may not need to include the images themselves, but code to produce any visualizations should be included in your analysis.)

## Requirements
This is a template for Python Projects in Goldenberg Lab. To use this template, please:

- Install Python and a version of conda (Anaconda or Miniconda). We recommend starting with the latest versions of each.
- ***You should run all of your code in a dedicated conda environment -- [see this guide on using conda!](conda_environments.md)*** When you're done, include the `environment.yml` in the root of this repo for others to use.

## Use this template for the first time (if you are not replicating/ adding on to an existing analysis)

- Choose the repository's username/organization name.
    - Please set the owner of your analysis template to our lab (`GoldenbergLab`).
    - All analysis repositories should start as public, unless indicated otherwise.
- Name the repository following the lab naming convention. Full guide on repository naming conventions can be found [here](https://github.com/GoldenbergLab/naming-conventions#repository-names). In short, github repositories are following this naming convention: `project-name-analysis`. So if your project is about counting kittens, your repository name is `counting-kittens-analysis`.
- Add a description of your project. Please include:
    1. Project Name
    2. Date of repository creation
    3. Your name, and the names of other who worked on it
    4. The purpose of the project and the main question you asked
    5. The source of the data for the analysis (Prolific, MTURK, Qualtrics, etc.)
