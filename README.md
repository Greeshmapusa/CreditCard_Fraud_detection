# Credit Card Fraud Detection using Logistic Regression
This project focuses on identifying fraudulent credit card transactions using a supervised machine learning model — Logistic Regression. It utilizes a publicly available dataset that contains anonymized transaction records, including both legitimate and fraudulent entries.

##  Project Objective

The goal is to:
- Analyze and understand the distribution of fraud and valid transactions.
- Train a logistic regression model to classify transactions.
- Evaluate model performance using classification metrics like precision, recall, and F1-score.


## Dataset Overview

- Total records: 284,807
- Features: Time, Amount, and 28 anonymized PCA components (`V1` to `V28`)
- Target: Class(0 = Legitimate, 1 = Fraudulent)
- Fraudulent transactions: only 492 (highly imbalanced)



## Techniques Used

- **Data Preprocessing:**
  - Feature scaling using `StandardScaler`
  - Train-test split (80/20)

- **Model**:
  - Logistic Regression (`max_iter=1000`)
  - Trained on scaled features

- **Evaluation**:
  - Confusion Matrix
  - Classification Report
  - Accuracy, Precision, Recall, F1-score
    

## Key Findings

- Fraudulent transactions are a very small fraction of the dataset.
- The `Amount` feature had to be scaled due to its variance.
- Logistic Regression model was able to detect some fraud, but performance can improve with class-balancing or other algorithms.



## Sample Results
Records of the Fraud transactions:
count    284315.000000
mean         88.291022
std         250.105092
min           0.000000
25%           5.650000
50%          22.000000
75%          77.050000
max       25691.160000
Name: Amount, dtype: float64

Records of valid transactions:
count     492.000000
mean      122.211321
std       256.683288
min         0.000000
25%         1.000000
50%         9.250000
75%       105.890000
max      2125.870000
Name: Amount, dtype: float64

Confusion Matrix:
[[56850    14]
 [   52    46]]
Classification Report:
              precision    recall  f1-score   support

           0       1.00      1.00      1.00     56864
           1       0.77      0.47      0.58        98

    accuracy                           1.00     56962
   macro avg       0.88      0.73      0.79     56962
weighted avg       1.00      1.00      1.00     56962


