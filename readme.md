# Credit Card Fraud Detection

## Project Overview
This project implements an end to end fraud detection system using machine learning on a highly imbalanced real world dataset. The objective is to detect fraudulent transactions effectively while balancing false positives, reflecting realistic operational constraints in financial systems.

Instead of focusing on accuracy, the project emphasizes recall, false negatives, PR AUC, and threshold tuning, which are critical for fraud detection use cases.

---

## Dataset
Source: Kaggle Credit Card Fraud Detection  
Description: Credit card transactions made by European cardholders  
Target variable: Class  
0 represents a normal transaction  
1 represents a fraudulent transaction  

Fraud rate is approximately 0.17 percent, indicating extreme class imbalance.

The raw dataset is not included in this repository due to size and licensing constraints.

---

## Exploratory Data Analysis
Key findings from exploratory data analysis include:

The dataset contains no missing values  
Fraudulent transactions are extremely rare, making accuracy misleading  
Transaction amount distributions for fraud and non fraud overlap heavily  
Fraud transactions are distributed across time with no clear temporal pattern  

These observations confirm that rule based heuristics are insufficient and motivate the use of machine learning models.

---

## Modeling Approach

### Logistic Regression Baseline
Logistic Regression was used as a baseline model due to its simplicity and interpretability. Class imbalance was handled using class weighting and features were standardized prior to training.

Results at threshold 0.50:

Fraud recall: 91.8 percent  
False negatives: 8  
False positives: 1336  
PR AUC: 0.726  

The model successfully detects most fraud cases but produces an impractically high number of false positives.

---

### Random Forest Model
Random Forest was trained to capture non linear feature interactions and improve ranking performance. Class imbalance was handled using balanced subsampling.

Initial results at threshold 0.50:

Fraud recall: 75.5 percent  
False negatives: 24  
False positives: 1  
PR AUC: 0.881  

Although precision is extremely high, recall is insufficient at the default threshold.

---

## Threshold Tuning
Multiple decision thresholds were evaluated to balance fraud recall and operational feasibility.

Final selected threshold: 0.10

Final Random Forest performance at threshold 0.10:

Fraud recall: 87.8 percent  
False negatives: 12  
False positives: 20  
Precision: 81.1 percent  
PR AUC: 0.881  

This configuration achieves a strong balance between fraud detection effectiveness and false positive control.

---

## Final Model Comparison

Model: Logistic Regression  
Threshold: 0.50  
Recall: 91.8 percent  
False negatives: 8  
False positives: 1336  
Precision: 6.3 percent  
PR AUC: 0.726  

Model: Random Forest  
Threshold: 0.10  
Recall: 87.8 percent  
False negatives: 12  
False positives: 20  
Precision: 81.1 percent  
PR AUC: 0.881  

---

## Final Decision
Random Forest with a decision threshold of 0.10 was selected as the final model due to superior ranking ability, strong fraud recall, significantly fewer false positives, and better real world usability.

---

## Technology Stack
Python  
Pandas  
NumPy  
Matplotlib  
scikit learn  
Jupyter Notebook  
Git and GitHub  

---

## Future Improvements
Cost sensitive threshold optimization  
Model explainability using SHAP  
Real time deployment using Streamlit or FastAPI  
Unsupervised fraud detection using Isolation Forest  

---

## Key Takeaway
This project demonstrates that fraud detection is not about maximizing accuracy, but about making informed trade offs using appropriate evaluation metrics and threshold tuning, which is essential for real world AI systems.
