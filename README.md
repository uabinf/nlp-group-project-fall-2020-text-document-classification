# Text-Document-Classification

For our project we wanted to explore the classification of long text documents using various methods.

# Introduction.
This project consists of 2 Phases.
**Phase1: Test Preliminary Models**
- Long short-term memory (LSTM) ✅
- Fine tune [BERT](https://arxiv.org/pdf/1810.04805.pdf) ✅
- Fine tune [RoBERTa](https://arxiv.org/pdf/1907.11692.pdf) ✅
**Phase2: Overcome the limited sequence length**
- Fine tune [Longformer](https://arxiv.org/pdf/2004.05150.pdf) (base 4096) ✅
- Recurrence over BERT ([RoBERT](https://arxiv.org/abs/1910.10781)). Not successful yet.

Thanks to the huggingface libraries, we were able to design this project in such a way that our model can be used to fine-tune BERT (and other similar models like RoBERTa) for any document classification problem (binary or multi-class including sentiment analysis) on various datasets with only minor changes necessary - just change the model from the config cell and adjust the dataset preprocessing cell. Please check notebooks/Fine_tuning_BERT_for_DC_seqLen512.ipynb for more details.

We mainly used **Python, Transformers, Pytorch, and Sklearn (plus Tensorflow and Gensim for LSTM)**.

# Experiment and Result

We fine-tuned BERT, RoBERTa, and Longformers to classify Fake/Real news from this dataset from Kaggle. We reached 98.74%, 99.79%, and 100% accuracy and 97.48%, 99.58%, and 100% MCC for these three models, respectively.
However, we found duplicate entries at the end of the project that affected the result. The experiment results after removing duplicates were 96.92%, 99.34%, 99.56% accuracy and 93.85%, 98.68%, 99.12% MCC.

**Post-Presentation**
Finally, we added a second Kaggle fake news dataset (which brought total rows from 6k to 25k), but the results only changed slightly (except for LSTM, which improved significantly).

# Data
The data we chose comprises two fake news dataset from Kaggle.

# Download the datasets:
1. Go to your Kaggle account, click on account and scroll to API section and click "Expire API Token" to remove previous tokens. 
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

    *Additional Setup (non-LSTM):*\
    •	Partition: pascalnodes\
    •	Number of CPU: 1\
    •	Memory per CPU (GB): 32

    *Additional Setup (LSTM - could not get it to run on GPU :():*\
    •	Partition: short\
    •	Number of CPU: 16\
    •	Memory per CPU (GB): 16
    
3. **Run notebooks 1-3 in sequence. (You may skip notebook 3_dataset_exploration.ipynb.)**
4. **Run any of the Jupyter Notebook files.** If needed, the !pip install requirements.txt is included in the main directory.
