# Customer Churn Prediction System - Analysis Report

## Dataset Description

The dataset contains 2,000 cleaned customer records after removing duplicates from the original file. It includes demographic, subscription, spending, engagement, support, payment, renewal, device, internet-speed, lifetime-value, and churn-status attributes. The target variable is `Churn`, encoded as `Yes` for churned customers and `No` for retained customers.

- Original records: 2,015
- Cleaned records: 2,000
- Duplicate rows removed: 15
- Missing values handled through model-pipeline imputation: 763
- Churn rate after cleaning: 30.0%

## Data Preparation Process

1. Removed duplicate rows to avoid over-counting repeated customers.
2. Dropped `Customer_ID` from modeling because it is an identifier, not a behavioral predictor.
3. Split the dataset into stratified training and test sets with an 80/20 ratio.
4. Imputed missing numeric values with medians and categorical values with most-frequent categories.
5. Standardized numeric columns and one-hot encoded categorical variables.

## Feature Engineering

The project adds behavior-focused features that summarize customer value, engagement, and service friction:

- `Avg_Spend_Per_Tenure`
- `Purchases_Per_Tenure`
- `Support_Requests_Per_Tenure`
- `Spend_Per_Purchase`
- `Engagement_Score`
- `Recent_Inactivity_Flag`
- `High_Support_Flag`

## Model Selection

Three supervised classification models were compared: Logistic Regression, Random Forest, and Gradient Boosting. The selected model is **Gradient Boosting**, chosen by ROC-AUC on the holdout test set.

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
| --- | ---: | ---: | ---: | ---: | ---: |
| Logistic Regression | 0.902 | 0.805 | 0.892 | 0.846 | 0.964 |
| Random Forest | 0.895 | 0.800 | 0.867 | 0.832 | 0.962 |
| Gradient Boosting | 0.892 | 0.818 | 0.825 | 0.822 | 0.967 |
| Tuned Random Forest | 0.887 | 0.782 | 0.867 | 0.822 | 0.964 |

## Evaluation Results

The best model achieved:

- Accuracy: 0.892
- Precision: 0.818
- Recall: 0.825
- F1 Score: 0.822
- ROC-AUC: 0.967
- Confusion Matrix: TN=258, FP=22, FN=21, TP=99

## Key Findings

Important churn indicators from the final model:

- Engagement_Score: 0.5493
- Login_Frequency: 0.1087
- Contract_Type_Monthly: 0.0814
- Last_Activity_Days_Ago: 0.0658
- Contract_Type_Yearly: 0.0276
- Purchases_Per_Tenure: 0.0261
- Auto_Renew_No: 0.0242
- Satisfaction_Score: 0.0232
- Auto_Renew_Yes: 0.0151
- Support_Requests_Per_Tenure: 0.0134
- Spend_Per_Purchase: 0.0111
- Customer_Lifetime_Value: 0.0065
- Number_of_Purchases: 0.0062
- Monthly_Spending: 0.0062
- Age: 0.0059

Customers with low engagement, long inactivity, lower satisfaction, high support-request intensity, and monthly or non-renewing contract behavior tend to show higher churn risk.

## Business Recommendations

- Prioritize outreach to customers with high predicted churn probability, especially those with low satisfaction and recent inactivity.
- Offer retention incentives for high-value customers before renewal deadlines.
- Improve support workflows for customers with repeated requests because support friction is a churn signal.
- Track engagement trends weekly and trigger campaigns when login frequency drops or inactivity exceeds 60 days.
- Use the model as a decision-support tool, not as the only decision maker; combine predictions with customer success context.

## Visual Evidence

Charts are available in `reports/figures/`, including churn distribution, spending and satisfaction comparisons, feature correlation, confusion matrix, ROC curve, and feature importance.
