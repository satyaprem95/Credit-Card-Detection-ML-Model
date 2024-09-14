# Credit-Card-Detection-ML-Model

Project Overview
This project aims to build a machine learning model to detect fraudulent credit card transactions. Given the highly imbalanced nature of the dataset, where fraudulent transactions are rare, the project uses various techniques like SMOTE to handle class imbalance, along with performance evaluation using precision, recall, F1-score, and ROC-AUC score.

Dataset
The dataset used for this project is a highly imbalanced dataset of European card transactions over two days, containing both fraudulent and non-fraudulent transactions. The columns include:

Time: Time elapsed between the transaction and the first transaction in the dataset.
V1 to V28: PCA-transformed features for anonymization.
Amount: Transaction amount in dollars.
Class: Target variable (0 for non-fraudulent, 1 for fraudulent).
Project Workflow
Data Exploration and Preprocessing:

Loaded the dataset and checked for missing values (no missing data found).
Performed Exploratory Data Analysis (EDA) to understand the distribution of fraud and non-fraud transactions.
Applied StandardScaler to scale the "Amount" and "Time" columns.
Handling Class Imbalance:

Used SMOTE (Synthetic Minority Over-sampling Technique) to generate synthetic data for the minority class (fraudulent transactions), balancing the dataset and preventing the model from being biased towards the majority class (non-fraudulent transactions).
Modeling:

A Random Forest classifier was trained on the dataset using balanced data.
Model accuracy was evaluated using the confusion matrix, classification report, and ROC-AUC score.
Threshold Tuning:

The default decision threshold (0.5) was adjusted to improve recall, leading to better fraud detection.
After tuning, the optimal threshold was found to be 0.28, resulting in improved recall but a slight drop in precision.
Performance Metrics:

Accuracy: 99.95%
Recall (fraud): Improved from 83% to 89% after threshold adjustment.
Precision (fraud): Dropped to 70% due to increased sensitivity and false positives.
F1-Score (fraud): 0.78 after threshold tuning.
ROC-AUC Score: 0.97
Results
The final model achieved a recall of 89% for fraudulent transactions, meaning it detects the majority of fraud cases, even with the trade-off of some false positives.
The precision dropped to 70% after lowering the threshold, reflecting an increase in false alarms, which is a common trade-off when prioritizing fraud detection.
