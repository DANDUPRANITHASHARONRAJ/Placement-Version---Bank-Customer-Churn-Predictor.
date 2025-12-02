📘 Bank Customer Churn Prediction (EDA + Feature Engineering + Stacking Ensemble)
📌 Project Overview

This project predicts customer churn for a bank using detailed EDA, advanced feature engineering, and a high-performance stacking ensemble model.
The goal is to identify customers at risk of leaving and provide actionable business insights.
📂 Dataset
The dataset contains customer-level information including demographics, financial behavior, product usage, and churn labels.
Key Columns

Demographics: Age, Gender, Geography

Financial: Balance, CreditScore, EstimatedSalary

Behavioral: Tenure, NumOfProducts, HasCrCard, IsActiveMember

Target: Exited (1 = churned, 0 = stayed)

🧹 Data Cleaning & Preprocessing

Normalized categorical columns (lowercasing, stripping whitespace)

Dropped ID-like columns not useful for modeling

Created categorical buckets:

Age groups

CreditScore (FICO categories)

Tenure groups

Engineered interaction features:

Balance-to-Salary Ratio

Products × Credit Card

Age × Tenure

Reduced skewness with log transforms for Balance & EstimatedSalary

Used Pipelines & ColumnTransformer to automate:

Numeric: median imputation + scaling

Categorical: mode imputation + one-hot encoding

📊 Exploratory Data Analysis (EDA)
Key Findings

Age is the strongest predictor of churn (older customers churn more)

Customers with only 1 product show much higher churn

Inactive customers are at high risk

Geography significantly affects churn

Salary, credit score, and gender have weak influence

Dataset is imbalanced (~21% churn, 79% non-churn)

Visualizations Included

Histograms for numeric features

Countplots for categorical features

Boxplots (Age vs Exited)

Correlation heatmap

Automated profiling report (ydata_profiling)

🧪 Feature Engineering

AgeGroup: binned ages (18–30, 31–40, etc.)

CreditBucket: FICO score categories

TenureGroup: grouped tenure (0–2, 3–5, 6–10)

BalanceSalaryRatio: financial behavior indicator

Products_Card: engagement feature (products × card)

AgeTenure: lifecycle interaction feature

LogBalance / LogSalary: reduced skew for better modeling

🤖 Modeling
Base Learners

XGBoost

LightGBM

CatBoost

Stacking Ensemble

A StackingClassifier with:

Level-1 models: XGB, LGBM, CatBoost

Level-2 (meta-model): Logistic Regression

predict_proba stacking for richer information

5-fold cross-validation

Sparse-to-dense conversion handled safely

Why Stacking?

Each boosting model captures different patterns.
Stacking combines them for better generalization and higher accuracy.

📈 Model Evaluation

Metrics used:

Accuracy

Precision

Recall (critical for churn)

F1-score

AUC-ROC (best for probability ranking)

The stacking ensemble demonstrated strong performance, especially in:

Recall → identifies actual churners

AUC-ROC → quality of probability predictions

📁 Project Outputs

bank_churn_cleaned.csv — cleaned dataset

bank_churn_data_dictionary.xlsx — full documentation of features

bank_churn_data_quality_report.html — automated profiling report

Visualization plots (histograms, countplots, boxplots, heatmaps)

🧠 Business Insights

Older customers are significantly more likely to churn

Customers with fewer products are at high churn risk

Inactive customers require targeted engagement

Churn varies by geography, indicating region-specific behavior

Salary, gender, credit score do not meaningfully drive churn
