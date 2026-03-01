# 🏠 Airbnb Price Prediction (CatBoost Regression)

This project focuses on predicting Airbnb listing prices using machine learning. The dataset was cleaned, preprocessed, and transformed before training a CatBoost Regressor model to estimate listing prices accurately.

## 📌 Project Overview
The project starts with exploratory data analysis (EDA), followed by data cleaning and preprocessing. Missing values were handled, duplicate records were removed, categorical and numerical features were processed, and new features were engineered. Finally, a CatBoost regression model was trained to predict listing prices.

## 🧹 Data Cleaning & Preprocessing
- Removed duplicate records.
- Converted price and service fee columns from string format (e.g., "$1,000") to numeric values.
- Replaced zero or invalid values with median values.
- Filled missing categorical values using mode.
- Filled missing numerical values using median.
- Standardized column names (lowercase, underscores).
- Dropped unnecessary columns such as house_rules, license, host_name, id, and host_id.
- Converted last_review to datetime format.
- Created new features:
  - property_age (2026 - construction_year)
  - days_since_last_review (difference between fixed date and last_review)
- Removed original construction_year and last_review after feature engineering.

## ⚙️ Feature Engineering
Two types of features were prepared:
- Numerical features scaled using StandardScaler.
- Categorical features encoded using OneHotEncoder (drop='first').

ColumnTransformer was used to combine preprocessing steps into a single pipeline.

## 🤖 Model Used
CatBoostRegressor was used because it handles categorical features efficiently and provides strong performance with minimal preprocessing.

Model configuration:
- iterations = 1000
- learning_rate = 0.05
- depth = 6
- eval_metric = RMSE
- random_seed = 42

The dataset was split into 80% training and 20% testing.

## 📊 Model Evaluation
Performance metrics used:
- RMSE (Root Mean Squared Error)
- R² Score

These metrics measure prediction accuracy and model performance.

## 🛠️ Technologies Used
Python, NumPy, Pandas, Matplotlib, Seaborn, Scikit-learn, CatBoost.

## 🚀 How to Run
1. Install required libraries:
pip install catboost
2. Load the dataset Airbnb_Open_Data.csv.
3. Run the notebook step by step.
4. Train the model and evaluate performance.
