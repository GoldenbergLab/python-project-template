# python-project-template

This is a template for Python Projects in Goldenberg Lab. To use this template, please

1. Download Anaconda and Python. We recommend starting with the latest Python version and Anaconda version. The tutorial [here](https://docs.jupyter.org/en/latest/install/notebook-classic.html) is helpful.
2. Create a virtual environment. Open the anaconda prompt and use the command `conda create -n environment python=3.9 anaconda`. You may need a different version of Python depending on what packages you need to work with. 
4. Within the virtual environment, update the `requirements.txt` to contain all the necessary packages for your project.
5. Designate your folders and files. We have provided a `processing` and `analysis` folder, but we recognize that your purposes for working in Python might be different. For example, if you have a Twitter data scraping project, you will want a separate Jupiter notebook or python script for each step of your data scraping project. The structure might look something like this:
    - 0 API scraping
    - 1 Data processing - cleaning, rows and columns
    - 2 Data processing - sentiment analysis 
    - 3 Data processing - merge sentiment with master data
