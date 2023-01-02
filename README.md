# Project Title: 
Towards Understanding the Impacts of Textual Dissimilarity on Duplicate Bug Report Detection

# Project Description: 
About 40% of software bug reports are duplicates of one another, which pose a major overhead during software maintenance. Traditional techniques often focus on detecting duplicate bug reports that are textually similar. However, in bug tracking systems, many duplicate bug reports might not be textually similar, for which the traditional techniques might fall short. In this paper, we conduct a large-scale empirical study to better understand the impacts of textual dissimilarity on the detection of duplicate bug reports. First, we collect a total of 92,854 bug reports from three open-source systems and construct two datasets containing textually similar and textually dissimilar duplicate bug reports. Then we determine the performance of three existing techniques in detecting duplicate bug reports and show that their performance is significantly poor for textually dissimilar duplicate reports. Second, we analyze the two groups of bug reports using a combination of descriptive analysis, word embedding visualization, and manual analysis. We found that textually dissimilar duplicate bug reports often miss important components (e.g., expected behaviors and steps to reproduce), which could lead to their textual differences and poor performance by the existing techniques. Finally, we apply domain-specific embedding to duplicate bug report detection problems, which shows mixed results. All these findings above warrant further investigation and more effective solutions for detecting textually dissimilar duplicate bug reports. 

# Members : 
Sigma Jahan, Mohammad Masudur Rahman

1. Dataset preprocessing: 
Run the files from Dataset Pre-processing for Eclipse, Firefox, and Mobile. We have used N-Gram to select the Textually Similar and Dissimilar Duplicate bug reports (Unigram, Bigram and Trigram). There are two sets of datatset from each category: One for the IR-based approach (Dataset for BM25 & LDA+GloVe and another for the DL-based approach (Train_Test dataset). Raw datasets are available upon request as the size is too huge to upload in GitHub.
Optional argument:

-   -d, --data            DATA
                        Path to data folder
-   -r, --ratio           SPLIT_RATIO
                         Split ratio of training data (default: 0.8)
-   -wv, --word_vocab     WORD_VOCAB_SIZE
                         Word vocabulary size (default: 20,000)
-   -cv, --char_vocab     CHAR_VOCAB_SIZE
                         Character vocabulary size (default: 100)


2. Existing Model Implementation and Evaluation: 
There are three main python files to run for each dataset. BM25, LDA+GloVE, and Siamese CNN as python files. All the files have been implemented using Google Colab with the following system requirements.
Optional arguments:

-   -h, --help            show this help message and exit
-   -d, --data            DATA
                         Path to data folder
-   -b, --baseline        BASELINE
                         Run with baseline model (default: False)
-   -k, --top_k           TOP_K
                         Number of top candidates for Recall@k evaluation (default: 25)
-   -e, --epochs          EPOCHS
                         Number of training epochs (default: 150)
-   -nw, --n_words        NUM_WORDS
                         Number of words in vocabulary (default: 20,000)
-   -nc, --n_chars        NUM_CHARS
                         Number of characters in vocabulary (default: 100)
-   -wd, --word_dim       WORD_DIM
                         Dimension of word embeddings (default: 100)
-   -cd, --char_dim       CHAR_DIM
                         Dimension of character embeddings (default: 50)
-   -nf, --n_filters      NUM_CNN_FILTERS
                         Number of filters for CNN (default: 64)
-   -np, --n_prop         NUM_PROPERTIES
                         Number of properties of the bug report (depending on data sets)
-   -bs, --batch_size     BATCH_SIZE
                         Batch size of training (default: 2064)
-   -nn, --n_neg          NUM_NEGATIVE_SAMPLES
                         Number of negative samples (default: 1)
-   -lr, --learning_rate  Learning rate (default: 1e-3)


3. Statistical Analysis:
 Run the file name as stat_analysis from Statistical Analysis folder with the following requirements (PyNonpar & Pingouin).

4. TSNE (Embedding Visualization):
 For the dataset-specific embedding visualization from the folder named Embedding Visualization, run the embedding_visualization python file on Google Colab.

5. Proposed Model Implementation and Evaluation: 
Run the domain_specific_embedding python file from the folder named as Domain-Specific Embedding Model for all three dataset. 

# System Requirements

- Python 3.7 - (All the files from the source code are written in python hence .ipynb file)
- PyTorch
- nltk
- kutils 0.3.0.
- gensim
- pyLDAvis
- PyNonpar
- Pingouin
- Tensorflow 2.8.0
- Keras 2.8.0
- Operating System: Windows 10 Home
- PC configuration:  16.0 GB RAM
- Make sure that GloVe is working on your platform. It is recommended to run the LDA+GloVE, Siamese CNN based model, and T-SNE visualization which include GloVe online on platforms such as Google Colab.


# Installation details: 
Install these packages using command prompt or using Google Colab: 
 
- pip install PyNonpar
- pip install Pingouin
- pip install kutils 0.3.0.
- pip install keras
- pip install Tensorflow
- pip install Python 3.7
- pip install PyTorch
- pip install nltk
- pip install gensim
- pip install pyLDAvis
- pip install GloVe
- pip install rank-bm25


 
Required parameters for the operations:
- Dup - Indicates duplicate bug reports
- Sim - Indicates textually similar duplicate bug reports
- Dissim - Indicates textually dissimilar duplicate bug reports


# Licensing Information:

https://www.freecodecamp.org/news/how-open-source-licenses-work-and-how-to-add-them-to-your-projects-34310c3cf94/

(Can get after creating the repo on Gitlab) - Use Apache License 2.0, MIT license, General Public License as you wish

Something not working as expected?
Contact: Sigma Jahan (sigma.jahan@dal.ca) 
