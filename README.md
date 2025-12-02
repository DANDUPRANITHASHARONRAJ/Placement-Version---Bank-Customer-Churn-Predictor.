Bank Customer Churn Prediction (EDA + Feature Engineering + Stacking Ensemble)
📌 Project Overview

This project analyzes bank customer churn using a combination of exploratory data analysis (EDA), feature engineering, and a powerful stacking ensemble model.
The goal is to identify patterns that lead customers to exit and to build a predictive model that can help the bank improve retention strategies.

📂 Dataset

Source: Customer data including demographics, account activity, products used, and churn label.

Key Columns

Demographics: Age, Gender, Geography

Financial: Balance, Credit Score, Estimated Salary

Behavioral: Tenure, Number of Products, Credit Card Ownership, Active Member Flag

Target: Exited (1 = churned, 0 = stayed)

🔍 Data Cleaning & Preprocessing

Handled duplicates and missing values using SimpleImputer

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

📊 Exploratory Data Analysis

Key findings from EDA:

Older customers churn more (strongest correlation with Exited)

Low product usage and inactive membership increase churn

Geography matters (some countries show higher exit rates)

Balance and salary are not strong standalone predictors

Dataset is imbalanced (~21% churn)

Visualizations included:

Histograms for numeric features

Countplots for categorical features

Correlation heatmap

Boxplots (Age vs Churn)

Automated HTML profiling report via ydata_profiling

🤖 Modeling Approach
Why Stacking Ensemble?

Different boosting models learn different patterns. Combining them increases stability and accuracy.

Base Models

XGBoost

LightGBM

CatBoost

Meta-Learner

Logistic Regression (using base models' predicted probabilities)

Cross-validation: 5-fold
Input: Sparse encoded features, safely converted to dense when required
🧪 Evaluation Metrics

Accuracy

Precision

Recall

F1-score

AUC-ROC

These metrics help measure:

the model’s ability to capture churners

probability calibration

performance on imbalanced data

📈 Results (Typical)

The stacking ensemble achieved strong balanced performance, especially in:

Recall → identifies actual churners

AUC-ROC → evaluates probability quality

This makes it well-suited for churn prediction use cases where catching churners is critical.

📁 Project Outputs

bank_churn_cleaned.csv — cleaned dataset ready for modeling

bank_churn_data_dictionary.xlsx — documentation of all features

bank_churn_data_quality_report.html — automated EDA report

Visualizations folder (optional)

🧠 Business Insights

Older customers (40+) churn significantly more

Customers with only 1 product are high-risk

Inactive members have higher churn probability

Geography impacts churn — location-based strategies can help

Salary, credit score, and gender have minimal predictive value
