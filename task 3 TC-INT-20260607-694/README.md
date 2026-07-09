# ⚡ Smart Electricity Consumption Prediction & Energy Optimization System

**TEYZIX CORE Internship Program — Task ID: ML-3 (Machine Learning Domain)**
Difficulty: Advanced (Industry-Based) | Submission Deadline: 09 July 2026

---

## 📁 Project Structure

```
teyzix_ml3/
├── data/
│   ├── household_electricity_dataset.csv     # Original raw synthetic dataset (656 records)
│   ├── processed_dataset.csv                 # After cleaning/encoding/scaling
│   ├── featured_dataset.csv                  # After feature engineering
│   └── DATASET_DOCUMENTATION.md              # Dataset collection methodology
├── notebooks/
│   └── ML3_Smart_Electricity_Analysis.ipynb  # Full pipeline, executed with outputs
├── src/
│   ├── generate_dataset.py                   # Original dataset generator
│   ├── preprocessing.py                      # Cleaning, encoding, scaling
│   ├── eda.py                                 # Exploratory Data Analysis + plots
│   ├── feature_engineering.py                # Feature selection/transformation
│   ├── train_models.py                       # Trains & compares 6 ML models
│   ├── recommendations.py                     # Energy optimization recommendation engine
│   ├── predict.py                             # CLI prediction interface
│   ├── app.py                                 # Streamlit web app (production interface)
│   └── generate_reports.py                    # Builds Excel + PDF reports
├── models/
│   ├── best_model.pkl                         # Trained best-performing model
│   ├── scaler.pkl, label_encoders.pkl         # Preprocessing artifacts
│   └── feature_list.pkl
├── reports/
│   ├── model_performance_report.csv
│   ├── feature_importance.csv
│   ├── Full_Report.xlsx                       # Dataset/Model/Energy/Forecast/Recommendations
│   └── Energy_Consumption_Report.pdf
├── plots/                                     # All EDA & evaluation visualizations
├── screenshots/                               # Add your own app screenshots here (see below)
├── requirements.txt
└── README.md
```

---

## 🚀 How to Run This Project (Step by Step)

### 1. Set up the environment
```bash
python3 -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 2. Run the full pipeline (in order)
```bash
cd src
python3 generate_dataset.py       # Step 1: Create the original dataset
python3 preprocessing.py          # Step 2: Clean, encode, scale
python3 eda.py                    # Step 3: Generate EDA plots
python3 feature_engineering.py    # Step 4: Feature selection & importance
python3 train_models.py           # Step 5: Train & compare 6 models, save the best one
python3 generate_reports.py       # Step 6: Build Excel + PDF reports
```

### 3. Try the CLI prediction tool
```bash
python3 predict.py
```
Answer the prompts (or press Enter to accept the shown defaults) to get an instant
prediction with recommendations.

### 4. Launch the interactive web app (recommended for demo/video)
```bash
streamlit run app.py
```
This opens a browser tab (usually `http://localhost:8501`) with a full interactive
form: enter household + appliance details and click **Predict Consumption** to see:
- Predicted daily & monthly electricity consumption
- Estimated monthly electricity bill
- Energy efficiency score (0–100)
- Peak usage hours
- Personalized energy-saving recommendations & estimated savings

### 5. Explore the full analysis notebook
Open `notebooks/ML3_Smart_Electricity_Analysis.ipynb` in Jupyter or VS Code — it already
contains all outputs (tables, plots, metrics) from an executed run, so you can view it
without re-running anything, or re-run it yourself (`Run All`) to reproduce everything
end-to-end.

---

## 🎥 Recording a Demo Video (for LinkedIn / submission)

A short screen-recording of the Streamlit app is the easiest way to show the system
working. Suggested flow (2–3 minutes):

1. **Start recording** (Windows: Xbox Game Bar `Win+G`; Mac: `Cmd+Shift+5`; or any free
   tool like OBS Studio).
2. Open a terminal, run `streamlit run app.py`, and let the browser tab open.
3. Briefly narrate: *"This is the Smart Electricity Consumption Prediction & Energy
   Optimization System built for TEYZIX CORE Task ML-3."*
4. Fill in a sample household (e.g., Independent House, 5 members, AC 7 hrs, Summer,
   38°C) and click **Predict Consumption**.
5. Walk through the results panel: predicted consumption, monthly bill, efficiency
   score, peak hours, and the recommendations.
6. (Optional) Show the notebook briefly — scroll through the correlation heatmap and
   the model comparison table.
7. Stop recording, trim if needed, and export as `.mp4`.
8. Upload the video to LinkedIn alongside your task-completion post (see Section 5.2 of
   the TEYZIX Internship Policies) and/or attach it to your GitHub repo's README as a
   demo GIF/link.

> Note: I can't generate an actual video file for you directly in this chat, but the
> app is fully built and ready — running the steps above will give you a clean,
> professional demo to record in just a couple of minutes.

---

## 📸 Screenshots
Take 3–4 screenshots while running the Streamlit app (input form, results panel,
recommendations) and place them in the `screenshots/` folder before zipping — this is
one of the required submission items.

---

## 📊 Key Results Summary

| Model | MAE | RMSE | R² Score |
|---|---|---|---|
| **Linear Regression (Best)** | 1.83 | 2.37 | **0.848** |
| Gradient Boosting | 1.90 | 2.61 | 0.816 |
| XGBoost | 1.90 | 2.62 | 0.815 |
| Random Forest | 1.95 | 2.70 | 0.803 |
| Support Vector Regression | 2.13 | 2.80 | 0.788 |
| Decision Tree | 2.34 | 3.72 | 0.625 |

**Top predictive factors:** AC usage hours, outdoor temperature, and heater usage
(seasonally) dominate daily electricity consumption — consistent with real-world
energy patterns.

---

## 🧩 Challenges Faced & Future Improvements

**Challenges:**
- Designing a synthetic data-generation process realistic enough to reflect true
  appliance-consumption relationships (not purely random) while keeping it fully
  original and reproducible.
- Balancing feature engineering complexity against model interpretability.

**Future Improvements:**
- Integrate a live Weather API for real-time temperature-based prediction adjustments.
- Add SHAP-based explainable AI visualizations for individual predictions.
- Deploy via Docker for one-command reproducibility.
- Extend to hourly (rather than daily) granularity using smart-meter-style time series.

---

## 👩‍💻 Submission Checklist (per TEYZIX Policy §5.3 / §3.3)
- [x] Complete Source Code (`src/`)
- [x] Original Dataset (CSV) + Documentation
- [x] Jupyter Notebook (executed with outputs)
- [x] Trained Model (`models/best_model.pkl`)
- [x] README.md (this file)
- [x] Project Report (Word document)
- [ ] GitHub Repository link (add after pushing)
- [ ] Screenshots (add your own from a live run)
- [ ] LinkedIn post with GitHub link + hashtags `#TEYZIXCORE #Internship #MachineLearning #TechInternship`
- [ ] ZIP file named `Task-3_<Your-Ref-ID>.zip`
