This code has been written my Adeepa Gustinna Wadu.


It contains codes to run the following integrative methods for dimension reduction as described in the manuscript.  

1. XVAE: the X-shape variational autoencoder without incorporating labels
2. MMVAE: the Conditional Mixed-Modal Variational Autoencoder without incorporating labels
3. CXVAE Type 1: Conditional integration variational autoencoder Type 1 (CXVAET1); for the integration of two datasets
4. CXVAE Type 2: Conditional integration variational autoencoder Type 2 (CXVAET2); for the integration of two datasets
5. CXVAESD: the CXVAE on a single dataset
6. CMMVAE: Conditional Mixed-Modal Variational Autoencoder; for the integration of two datasets
7. EXTCXVAE: Extended CXVAE to integrate 3 datasets
8. PCA: The principal component analysis approach. The reduced dimension is used to train the stat leaning methods similar to principal component regression (PCR)
9. Concat: The datasets are just concanated/merged before been applied to the following statistical/machine learning methods
   

The aforementioned methods provide inputs or latent variables (reduced data) to run statistical/machine learning methods in the second stage to predict labels.
Those methods are: 
1. Naive Bayes
2. Random Forest
3. Support Vector Machines (SVM) (Linear and non-linear)
4. Neural Networks
5. Logistic Regression

Here is the description of files:

1. Conditional_Integration_Run.ipynb: A Jupyter file that contains script to run integrative methods for dimension reduction (methods 1 to 9)
2. conditional_integration.py: This python file contains all the functions necessary to run the methods.
   It also saves latent spaces (i.e the reduced dimension) used to run the stat learning methods
3. Y_PAM50_PP.csv: Intrinsic gene-expression sub-types (label variable) from the metabric data
4. rna_Preprocessed.csv: mRNA expression from the metabric data,
5. clin_Preprocessed.csv: clinical data from the metabric data
6. cna_Preprocesse.csv: somatic copy number aberrations from the metabric data
7. X1LS.csv: A "linear" simulated dataset 1 
8. X1LS.csv: A "linear" simulated dataset 2 
9. Y_PP.csv: Label variable generated from the shared latent variable between X1LS and X2LS
10. X1_3LS.csv: A "linear" simulated dataset 1 
11. X2_3LS.csv: A "linear" simulated dataset 2 
12. X3_3LS.csv: A "linear" simulated dataset 3 
13. Y_3PP.csv: Label variable generated from the shared latent variable between the 3 datasets: X1_3LS, X2_32LS and X3_32LS
14. Data_Preprocessing.ipynb: this file provides steps to pre-process data before fitting it via to our architectures
   

   Input Data information

1. When adding input datasets to the “Conditional_Integration_Run.ipynb” notebook, they should be scaled between 0 and 1, with rows representing samples and columns representing features. The datasets should be provided in Excel CSV format. These input files will be automatically converted into matrix form within the corresponding functions (e.g., CXVAET1, CXVAET2, etc.) inside the “conditional_integration.py” file.

2. When adding target variable to the “Conditional_Integration_Run.ipynb” notebook, the target outcome variable should be one-hot encoded. For example, in the METABRIC dataset, the PAM50 target variable, which has 5 class labels, should be encoded using five separate columns as shown below:

LumA LumB Basal Her2 Normal
1     0    0     0    0
0     1    0     0    0
0     1    0     0    0

...   ... ...   ...   ...


Reference:  Adeepa Gustinna, Karen Kopciuk, and Thierry Chekouo (2025): A multi-omic data integration approach via Conditional Variational Autoencoders, submitted. 