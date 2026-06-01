# Customer-Churn
Telco Customer Churn Prediction with Random Forest and AdaBoost
Customer churn prediction using Random Forest and a custom AdaBoost implementation. Includes preprocessing, feature engineering, model evaluation, and ensemble learning analysis on the Telco Customer Churn dataset.
# Telco Customer Churn Prediction

## Overview

This project predicts customer churn using the Telco Customer Churn dataset. The objective is to identify customers who are likely to discontinue their telecommunications services based on demographic information, account details, and subscribed services.

The project includes:

* Data preprocessing and cleaning
* Exploratory data analysis
* Feature encoding and scaling
* Random Forest classification
* Custom AdaBoost implementation from scratch
* Performance evaluation using multiple classification metrics

---

## Dataset

The Telco Customer Churn dataset contains information about 7,043 customers and whether they left the company within the last month.

### Features

* Gender
* Senior Citizen Status
* Partner and Dependents
* Tenure
* Phone Service
* Internet Service
* Online Security
* Online Backup
* Device Protection
* Tech Support
* Streaming Services
* Contract Type
* Payment Method
* Monthly Charges
* Total Charges

### Target Variable

* Churn = Yes (Customer leaves)
* Churn = No (Customer stays)

Dataset Distribution:

* No Churn: 5,174 customers
* Churn: 1,869 customers

The dataset is moderately imbalanced, with significantly more customers staying than leaving.

---

## Data Preprocessing

The following preprocessing steps were performed:

1. Loaded the dataset using Pandas.
2. Checked for missing values.
3. Converted `TotalCharges` to a numeric feature.
4. Replaced missing values with the median value.
5. Encoded categorical variables using LabelEncoder.
6. Split the data into training and testing sets.
7. Standardized features using StandardScaler.

---

## Models Implemented

### 1. Random Forest Classifier

A Random Forest model was trained as a baseline ensemble learning method.

Key characteristics:

* Multiple decision trees
* Bagging-based ensemble learning
* Reduced overfitting
* Improved generalization performance

---

### 2. Custom AdaBoost Classifier

AdaBoost was implemented from scratch using Decision Stumps (`DecisionTreeClassifier(max_depth=1)`) as weak learners.

Implementation includes:

* Sample weight initialization
* Weighted error calculation
* Alpha (learner weight) computation
* Sample weight updating
* Weighted voting for final prediction

Because AdaBoost requires labels in the format {-1, +1}, the target values were converted from {0, 1} before training.

---

## Results

### Random Forest Performance

| Metric    | Score |
| --------- | ----- |
| Accuracy  | 0.80  |
| Precision | 0.67  |
| Recall    | 0.47  |
| F1 Score  | 0.55  |
| ROC-AUC   | 0.69  |

#### Interpretation

The Random Forest model achieved an accuracy of 80%, indicating strong overall performance.

A precision of 67% means that when the model predicts a customer will churn, it is correct most of the time. The recall score of 47% shows that the model identifies nearly half of all customers who actually churned.

The ROC-AUC score of 0.69 demonstrates moderate ability to distinguish between churning and non-churning customers.

Overall, Random Forest provides reliable and balanced performance for churn prediction.

---

### Custom AdaBoost Performance

| Metric    | Score |
| --------- | ----- |
| Accuracy  | 0.81  |
| Precision | 0.66  |
| Recall    | 0.55  |
| F1 Score  | 0.60  |
| ROC-AUC   | 0.72  |

#### Interpretation

The custom AdaBoost implementation achieved the highest overall performance among the tested models.

Compared to Random Forest:

* Higher accuracy (81% vs 80%)
* Higher recall (55% vs 47%)
* Higher F1 score (0.60 vs 0.55)
* Better ROC-AUC (0.72 vs 0.69)

The improved recall is particularly important in churn prediction because identifying customers at risk of leaving is often more valuable than maximizing overall accuracy.

The ROC-AUC score of 0.72 indicates that AdaBoost has a stronger ability to separate churning customers from non-churning customers.

---

## Model Comparison

| Metric    | Random Forest | AdaBoost |
| --------- | ------------- | -------- |
| Accuracy  | 0.80          | 0.81     |
| Precision | 0.67          | 0.66     |
| Recall    | 0.47          | 0.55     |
| F1 Score  | 0.55          | 0.60     |
| ROC-AUC   | 0.69          | 0.72     |

### Conclusion

Both ensemble learning methods performed well on the Telco Customer Churn dataset. However, the custom AdaBoost implementation slightly outperformed Random Forest across most evaluation metrics.

AdaBoost achieved:

* Better churn detection capability
* Higher recall
* Better F1 score
* Stronger ROC-AUC performance

These results suggest that boosting weak learners can effectively improve customer churn prediction and may be a preferred approach for this dataset.

---

## Technologies Used

* Python
* NumPy
* Pandas
* Scikit-learn
* Matplotlib
* Seaborn

---

## How to Run

Clone the repository:

```bash
git clone https://github.com/yourusername/telco-customer-churn.git
cd telco-customer-churn
```

Install dependencies:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

Place the dataset file in the project directory:

```text
Telco-Customer-Churn.csv
```

Run the script:

```bash
python telco_customer_churn.py
```

---

## Future Improvements

* Hyperparameter tuning
* Cross-validation
* Feature importance analysis
* XGBoost implementation
* Class imbalance handling using SMOTE
* ROC Curve visualization
* Additional ensemble model comparisons

---

## Author

Machine Learning Project – Telco Customer Churn Prediction using Ensemble Learning Techniques.

