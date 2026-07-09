# ⚡ Task 3 — Smart Electricity Consumption Prediction & Energy Optimization System

**TEYZIX CORE Internship Program — June Batch**
**Task ID:** ML-3 | **Domain:** Machine Learning | **Difficulty:** Advanced (Industry-Based)
**Ref ID:** TC-INT-20260607-694

---

## 📌 Project Overview

A production-ready **Smart Electricity Consumption Prediction & Energy Optimization System** built using Machine Learning. The system predicts a household's daily electricity consumption based on appliance usage and environmental factors, and generates personalized, actionable energy-saving recommendations.

---

## 🛠️ Tech Stack

Python, Pandas, NumPy, Scikit-learn, XGBoost, Matplotlib, Seaborn, Streamlit, Joblib, OpenPyXL, ReportLab, Jupyter Notebook

---

## 📁 Repository Structure

```
task 3 TC-INT-20260607-694/
├── data/
│   ├── household_electricity_dataset.csv     # Original synthetic dataset (650+ records)
│   └── DATASET_DOCUMENTATION.md               # Dataset generation methodology
├── notebooks/
│   └── ML3_Smart_Electricity_Analysis.ipynb   # Full pipeline notebook (executed)
├── src/
│   ├── generate_dataset.py
│   ├── preprocessing.py
│   ├── eda.py
│   ├── feature_engineering.py
│   ├── train_models.py
│   ├── recommendations.py
│   ├── predict.py                             # CLI prediction interface
│   ├── app.py                                 # Streamlit web app
│   └── generate_reports.py
├── models/
│   └── best_model.pkl                         # Trained model (Linear Regression)
├── reports/
│   ├── Full_Report.xlsx
│   ├── Energy_Consumption_Report.pdf
│   └── TEYZIX_ML3_Project_Report.docx
├── plots/                                     # EDA & evaluation visualizations
├── screenshots/
├── requirements.txt
└── README.md
```

---

## 🚀 How to Run

```bash
pip install -r requirements.txt
cd src
python3 generate_dataset.py
python3 preprocessing.py
python3 eda.py
python3 feature_engineering.py
python3 train_models.py
python3 generate_reports.py

# CLI prediction
python3 predict.py

# Web app
streamlit run app.py
```

---

## 📊 Results

| Model | MAE | RMSE | R² Score |
|---|---|---|---|
| **Linear Regression (Best)** | 1.83 | 2.37 | **0.848** |
| Gradient Boosting | 1.90 | 2.61 | 0.816 |
| XGBoost | 1.90 | 2.62 | 0.815 |
| Random Forest | 1.95 | 2.70 | 0.803 |
| Support Vector Regression | 2.13 | 2.80 | 0.788 |
| Decision Tree | 2.34 | 3.72 | 0.625 |

**Key Insight:** AC usage hours and outdoor temperature are the strongest drivers of daily electricity consumption.

---

## ✨ Features

- Original synthetic dataset (no public/Kaggle data used)
- Full preprocessing pipeline (missing values, duplicates, outliers, encoding, scaling)
- Comprehensive EDA with correlation heatmaps, distributions, box/scatter plots
- 6 regression models trained and compared
- Interactive Streamlit prediction app with:
  - Predicted daily/monthly consumption
  - Estimated electricity bill
  - Energy efficiency score
  - Peak usage hours
  - Personalized energy-saving recommendations
- Automated Excel/PDF/CSV report generation
- Full documentation and executed Jupyter notebook

---

## 👩‍💻 Author

**Bushra Khan (Khanum)**
BS Computer Science, Sukkur IBA University (Batch 2026)
TEYZIX CORE Internship — June Batch

---

#TEYZIXCORE #Internship #MachineLearning #TechInternship
