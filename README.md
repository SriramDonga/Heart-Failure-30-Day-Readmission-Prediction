# Heart-Failure-30-Day-Readmission-Prediction
Machine Learning project for predicting 30-day heart failure readmission
# Heart Failure 30-Day Readmission Prediction

## Project Overview

This project focuses on predicting whether a patient will be readmitted within 30 days after a heart-failure-related hospitalization.

The objective is to use machine learning to identify patients at higher risk of 30-day readmission. Early identification can help healthcare teams prioritize follow-up, discharge planning, and post-discharge support.

## Dataset

The dataset contains **12,000 patient records**.

The target variable is:

- `Readmitted_30_Days` — indicates whether the patient was readmitted within 30 days.

The `Patient_ID` column was treated as an identifier and excluded from model training.

## Data Preparation

The project included:

- Initial dataset inspection
- Missing-value checks
- Duplicate checks
- Data-type and value validation
- Categorical feature analysis
- Numerical feature analysis
- Target distribution analysis
- Correlation analysis
- Data leakage checks
- Removal of the patient identifier
- Train-test splitting using an 80/20 split
- Stratification of the target variable
- Standardization of numerical features
- One-hot encoding of categorical features

The preprocessing steps were fitted using the training data to help prevent data leakage into the test set.

## Machine Learning Models

Three binary classification models were trained and evaluated:

1. Logistic Regression
2. K-Nearest Neighbors (KNN)
3. Decision Tree

Hyperparameter experiments were performed using cross-validation to improve model settings.

### Final Hyperparameters

| Model | Final Hyperparameter |
|---|---|
| Logistic Regression | `C=0.1`, `solver='liblinear'` |
| KNN | `k=31` |
| Decision Tree | `max_depth=6` |

## Final Model Performance

The final models were evaluated using Accuracy, Precision, Recall, F1-Score, and ROC-AUC.

| Model | Test Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 0.8942 | 0.8520 | 0.7833 | 0.8162 | 0.9561 |
| KNN | 0.8496 | 0.8811 | 0.5764 | 0.6969 | 0.9271 |
| Decision Tree | 0.8450 | 0.7862 | 0.6639 | 0.7199 | 0.8947 |

## Model Validation

Training and test performance were compared to assess generalization.

The final models did not show strong evidence of severe overfitting or underfitting based on the train-test ROC-AUC comparison.

The ROC-AUC gaps were:

- Logistic Regression: 0.0025
- KNN: 0.0127
- Decision Tree: 0.0223

## Evaluation and Visualizations

The notebook includes:

- Target class distribution
- Exploratory data analysis
- Feature relationships
- Confusion matrices
- True Positive, True Negative, False Positive, and False Negative interpretation
- Model performance comparison
- ROC curves with AUC values
- Train vs. test performance comparison
- Hyperparameter tuning and cross-validation results

## Final Model

Based on the final test-set results, **Logistic Regression** achieved the highest test Accuracy, Recall, F1-Score, and ROC-AUC among the three evaluated models.

Its final test ROC-AUC was **0.9561**.

However, before real-world clinical use, the model would require further validation on independent clinical data and assessment of factors such as class imbalance, feature availability, threshold selection, and potential data leakage.

## Project Structure

```text
Heart-Failure-30-Day-Readmission-Prediction/
│
├── data/
│   └── dataset_12000_records.csv
│
├── notebooks/
│   └── Month_1_Heart_Failure_Readmission.ipynb
│
└── README.md
