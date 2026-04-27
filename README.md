# DNA Promoter Classification using Machine Learning

## Overview
This project focuses on the binary classification of DNA sequences into **promoter** and **non-promoter** regions using classical machine learning techniques.

A promoter is a regulatory DNA region located upstream of a gene. It plays a key role in gene expression by serving as a binding site for RNA polymerase and transcription factors, helping initiate transcription. Identifying promoter regions is therefore relevant for understanding gene regulation and for broader applications in bioinformatics and genomics.

The goal of this project is to transform DNA sequences into numerical representations, compare several machine learning classifiers, and evaluate their ability to distinguish promoter from non-promoter sequences.

---

## Dataset
The project uses the **UCI Molecular Biology (Promoter Gene Sequences) dataset**, containing labeled DNA sequences from promoter and non-promoter classes.

Each sample includes:
- a class label (`+` for promoter, `-` for non-promoter)
- an identifier
- a DNA sequence

---

## Project Workflow

### 1. Data loading
The dataset is loaded from a raw text file and organized into a pandas DataFrame.

### 2. Sequence preprocessing
Each DNA sequence is split into individual nucleotides, and tab characters are removed.  
Each nucleotide position is treated as a categorical feature.

### 3. Feature encoding
Since nucleotides are categorical variables, **one-hot encoding** is applied to transform the sequence positions into numerical features suitable for machine learning models.

### 4. Train-test split
The data is split into training and test subsets using **stratified sampling** to preserve class balance.

### 5. Model comparison
The following classifiers are evaluated:

- K-Nearest Neighbors
- Gaussian Process Classifier
- Decision Tree
- Random Forest
- Neural Network (MLP)
- AdaBoost
- Gaussian Naive Bayes
- SVM (Linear)
- SVM (RBF)
- SVM (Sigmoid)

### 6. Evaluation
Model performance is assessed through:
- **10-fold cross-validation** on the training set
- **test accuracy**
- **classification report**
- **confusion matrix**
- **ROC curve comparison for the top 3 models**

---

## Main Results
The project shows that promoter and non-promoter DNA sequences contain recognizable patterns that can be captured by machine learning models after suitable encoding.

The comparison of multiple classifiers highlights that standard ML methods can already provide meaningful predictive performance on this sequence classification task.

Because the dataset is relatively small and simplified, the results should be interpreted with caution and seen primarily as a bioinformatics-oriented machine learning demonstration project.

---

## Repository Structure

```text
dna-promoter-classification/
│── README.md
│── requirements.txt
│── data/
│   └── raw/
│       └── promoters.data.txt
│── notebooks/
│   └── dna_promoter_classification.ipynb
```

---

## How to Run

```bash
pip install -r requirements.txt
jupyter notebook
```

---

## Topic Covered

- Python
- pandas
- scikit-learn
- feature encoding
- cross-validation
- ROC-AUC
- bioinformatics preprocessing

---

## Limitations

- Small and simplified benchmark Dataset
- Not a full genomics / NSG pipeline
- One-hot encoding does not capture long-range sequence dependencies

---

## Future Work

- Hyperparameter tuning
- Deep learning models
- Larger genomic datasets