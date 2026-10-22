# Customer Churn Prediction

Predicting which telecom customers will leave, so the business can act before they go.

## Problem
26.5% of customers churned. The goal is to identify at-risk customers early.

## Dataset
IBM Telco Customer Churn: 7,043 customers, 21 features.

## Key Findings
- Month-to-month contracts churn at 43%, vs 3% for two-year contracts.
- Most churn happens in the first months of tenure.
- Fiber optic customers churn at 42%.
- Churners pay higher monthly bills.

## Approach
- Cleaning: fixed TotalCharges (11 blanks for new customers set to 0)
- Encoding: one-hot encoding
- Scaling: StandardScaler
- Imbalance: compared class weights vs SMOTE
- Models: Logistic Regression, Random Forest, XGBoost (tuned with GridSearchCV, 5-fold CV)

## Results
| Model | ROC-AUC | Churn Recall |
|---|---|---|
| Logistic Regression (balanced) | 0.841 | 0.79 |
| XGBoost (tuned) | 0.844 | 0.79 |
| Random Forest | 0.825 | 0.50 |

Final model: Logistic Regression. Same performance as XGBoost, but simpler and explainable.

## Business Recommendations
1. Move month-to-month customers to longer contracts with discounts.
2. Run an onboarding program for the first 6 months.
3. Review fiber optic pricing and service quality.

## Tools
Python, pandas, matplotlib, seaborn, scikit-learn, imbalanced-learn, XGBoost, joblib