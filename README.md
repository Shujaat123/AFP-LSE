# AFP-LSE
AFP-LSE: Antifreeze Proteins Prediction Using Latent Space Encoding of Composition of k-Spaced Amino Acid Pairs

# Requirements
- Python >= 3.5.4
- Tensorflow = 1.13.1
- Keras = 2.2.4

# Description
The deep learning model is implemented using Python on Keras (Tensorflow). The necessary files to run the model have been uploaded. 
For verification purposes, a trained model has been uploaded with necessary data files. For self implementation, the model file has also been uploaded and the procedure of extracting features is described below.

# Dataset
The dataset is obtained from Kandaswamy et. al containing 481 antifreeze proteins and 9193 non-antifreeze proteins.
A dataset file named "Dataset.csv" contains the aforementioned samples.

# Features
The features from the dataset are extracted using CKSAAP encoding scheme. 
# Composition of k-Spaced Amino Acid Pairs (CKSAAP)
This scheme reflects the amino acid pair information in small and large range with in the peptides depending upon the value of k(gap).

The encoding scheme is utilized from iFeature web server using following download link: 
(https://github.com/Superzchen/iFeature)
Chen Z, Zhao P, Li F, Leier A, Marquez-Lago TT, Wang Y, Webb GI, Smith AI, Daly RJ*, Chou KC*, Song J*. iFeature: a python package and web server for features extraction and selection from protein and peptide sequences. Bioinformatics, 2018, Volume 34, Issue 14, 15 July 2018, Pages 2499–2502, doi: 10.1093/bioinformatics/bty140.

# Feature Extraction
The CKSAAP feature descriptors can be extracted using the command: 

**path/iFeature-master>python iFeature.py --file xyz/test-protein.txt --type CKSAAP --out xyz/test-protein-features.txt**

The CKSAAP feature encoding calculates the frequency of amino acid pairs separated by any k residues. The default value of k is 5. To change the default value of k, open "CKSAAP.py" and replace gap="5" in line # 20 to any other integer > 0. A file named "placeholder.txt" has been uploaded with the aforementioned modification in line 20 of "CKSAAP.py".  The features used in this paper were extracted by selecting the value of k=8.

A sample feature file has been uploaded named "Sample_Features.csv"


