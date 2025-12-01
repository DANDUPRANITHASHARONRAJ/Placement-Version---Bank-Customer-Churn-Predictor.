# Placement-Version---Bank-Customer-Churn-Predictor.

📘 Bank Customer Churn Analysis 

A complete walkthrough of understanding, cleaning, exploring, and preparing the dataset for churn prediction.

📝 Project Overview

Customer churn is a major concern for subscription-based and service-driven businesses. This project performs Exploratory Data Analysis (EDA) and data preprocessing on a bank churn dataset to understand customer behavior and prepare the data for machine-learning modeling.

The notebook includes:

Data understanding

Data cleaning

Feature engineering

Outlier handling

Encoding

Scaling

Class imbalance handling

Exploratory insights

Pre-modeling transformations

This README summarizes the process and results in a clean, easy-to-understand format.

📂 1. Dataset Summary

The dataset contains demographic, financial, and behavioral information about bank customers, including whether they churned or stayed.

Key Columns

Customer demographics: Gender, Age, Geography

Account information: Tenure, Balance, Estimated Salary

Behavior: Num of Products, Credit Score, Has Credit Card, Is Active Member

Target: Exited (1 = churned, 0 = stayed)

🧹 2. Data Cleaning & Preparation
✔ Missing Values

No major missing values were found (per the notebook's profiling report).

✔ Duplicate Handling

Duplicate records were checked and removed if necessary.

✔ Data Type Fixes

Categorical features converted to proper categorical types.

✔ Outlier Treatment

Outliers in Age, Balance, CreditScore handled carefully.

Decision: Keep outliers if they represent real customer behavior.

Boxplot distributions examined.

🧩 3. Feature Engineering
New features created (based on notebook logic):

Age groups

Customer activity flags

Financial ratio calculations (e.g., balance-to-salary ratio)

These features can help improve model learning.

🔠 4. Encoding & Transformation
✔ Categorical Encoding

Gender, Geography → One-Hot Encoding

Binary flags → mapped to 0/1

✔ Scaling

Numeric columns scaled using StandardScaler

Important for distance-based models and neural nets

✔ Train/Test Consistency

A robust transformation pipeline ensures new unseen customer data can be processed with the same rules.

⚖ 5. Handling Class Imbalance

Customer churn datasets are typically imbalanced (few customers churn).
The notebook applied:

Oversampling using SMOTE

Achieved a more balanced 1:1 ratio

Ensures models do not become biased toward predicting "not churn"

📊 6. Exploratory Data Analysis (EDA)
✔ Univariate Analysis

Histograms and distributions of key variables

Summary statistics

Outlier visualization

✔ Bivariate Analysis

Key relationships identified:

Age vs Churn: Older customers churn more

Active Members: Inactive customers have much higher churn

NumOfProducts: Customers with 3–4 products churn significantly

Geography Influence: Some regions have higher churn

Balance & Salary: Weak direct relationship with churn

✔ Correlation Heatmap

Identified correlations among:

Age

Tenure

Credit Score

Activity status

Churn

🧠 7. Pre-Modeling Pipeline

The notebook produces a clean ML-ready dataset:

Includes:

Encoded & scaled features

Engineered variables

Balanced target classes

Training/testing split

Output:

X_train, X_test, y_train, y_test

Ready for classification models such as:

Logistic Regression

Random Forest

XGBoost

Gradient Boosting

Neural Networks

✅ 8. Project Milestones Completed

✔ Data understanding
✔ Cleaning & preprocessing
✔ Exploratory data analysis
✔ Pandas Profiling report
✔ Outlier inspection
✔ Encoders & scalers applied
✔ SMOTE oversampling
✔ Feature engineering
✔ Pipeline for reusability

📁 9. Project Structure
.
├── FINAL_EDA_BANK_CHURN_CORRECTED VERSION.ipynb
├── README.md
└── data/
    └── bank_churn.csv  (not included here)

🚀 10. Next Steps (Modeling Suggestions)

Recommended modeling flow:

Train baseline Logistic Regression

Compare with Random Forest & XGBoost

Tune hyperparameters

Evaluate using:

Recall (important for churn!)

F1 score

ROC-AUC

Deploy model or create an inference API

🎯 Summary

This notebook fully prepares the dataset for predictive churn modeling through a complete EDA and processing pipeline.
It ensures:

Cleaned high-quality data

Balanced classes

Well-structured features

Ready-to-train ML inputs
