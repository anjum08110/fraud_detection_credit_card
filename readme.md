# Credit Card Fraud Detection

## Project Overview
This project focuses on detecting fraudulent credit card transactions using machine learning techniques on a highly imbalanced dataset. The goal is to maximize fraud detection recall while understanding the trade-off with false positives.

## Dataset
- Source: Kaggle – Credit Card Fraud Detection
- Transactions by European cardholders
- Fraud cases represent ~0.17% of the data

## Exploratory Data Analysis
- Verified no missing values
- Analyzed severe class imbalance
- Studied transaction amount and time distributions
- Observed strong overlap between fraud and non-fraud cases, motivating machine learning models

## Modeling Approach
- Baseline model: Logistic Regression
- Class imbalance handled using class weights
- Features standardized before modeling

## Evaluation Metrics
Due to extreme class imbalance, accuracy is misleading. The following metrics were used:
- Precision
- Recall
- F1-score
- PR-AUC

## Results (Logistic Regression)
- Fraud Recall: ~91.8%
- Fraud Precision: ~6.3%
- PR-AUC: ~0.73

The model successfully detects most fraudulent transactions while accepting a higher false positive rate, which is a common and acceptable trade-off in fraud detection systems.

## Next Steps
- Threshold tuning to optimize business cost
- Train and compare a Random Forest model
- Final model selection
