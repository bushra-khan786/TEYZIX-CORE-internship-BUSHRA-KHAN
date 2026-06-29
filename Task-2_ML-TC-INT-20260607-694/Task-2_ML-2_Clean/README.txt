Customer Churn Prediction System - TEYZIX ML Task 2

Short Description:
This project predicts customer churn using a realistic customer dataset, preprocessing, feature engineering, model comparison, evaluation metrics, feature importance, and a command-line prediction interface.

How to Run:
1. Install dependencies:
   pip install -r requirements.txt

2. Train and evaluate the model:
   python src/train_model.py

3. Predict churn for a customer:
   python src/predict_churn.py --json "{\"Age\":41,\"Gender\":\"Male\",\"City\":\"Nashville\",\"Subscription_Type\":\"Premium\",\"Monthly_Spending\":108.84,\"Tenure_Months\":8,\"Number_of_Purchases\":3,\"Support_Requests\":6,\"Login_Frequency\":0,\"Last_Activity_Days_Ago\":32,\"Satisfaction_Score\":4,\"Payment_Method\":\"Credit Card\",\"Contract_Type\":\"Quarterly\",\"Discount_Used\":\"No\",\"Referral_Source\":\"Email Campaign\",\"Auto_Renew\":\"No\",\"Device_Type\":\"Desktop\",\"Internet_Speed\":\"Fast\",\"Customer_Lifetime_Value\":1130.76}"

Main Deliverables:
- customer_churn_dataset.csv
- src/train_model.py
- src/predict_churn.py
- models/churn_model.joblib
- models/model_metadata.json
- reports/analysis_report.md
- reports/figures/
- notebooks/customer_churn_prediction.ipynb
- screenshots/
