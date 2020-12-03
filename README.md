# Text-Document-Classification

For our project we wanted to explore the classification of long text documents using various methods.

The dataset we used was a fake news dataset from Kaggle.


# Download the dataset:
1. Go to your kaggle account, click on account and scroll to API section and click "Expire API Token" to remove previous tokens. 
2. Click on "Create New API Token" - it will download kaggle.json to your machine.
3. Move the downloaded kaggle.json to the /notebooks directory
4. Run dowload_from_kaggle.ipynb. It contain shell commands that can be run from the shell

# Explore the dataset.
To explore the dataset, please check the Datasets_Exploration.ipynb file. 

# Run the code on Cheaha:
To run the Project on Cheaha
1.	**Clone the project from github to the desired directory**\
    git clone https://github.com/uabinf/nlp-group-project-fall-2020-text-document-classification.git

2.	**Start a Jupyter Notebook server with the following settings.**\
    *Environment Setup:*\
    module load cuda92/toolkit/9.2.88\
    module load CUDA/9.2.88-GCC-7.3.0-2.30

    *Additional Setup:*\
    •	Extra jupyter arguments: --notebook-dir=/data/user/$USER if you want to change the home directory to the data folder\
    •	Number of Hours: 3\
    •	Partition: pascalnodes\
    •	Number of CPU: 1\
    •	Memory per CPU (GB): 32
    
3. **Download the dataset.**	
4. **Run any of the Jupyter Notebook files.** If needed, the !pip install requirements.txt is included in the files.
