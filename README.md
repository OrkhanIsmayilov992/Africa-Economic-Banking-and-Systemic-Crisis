# 🌍 Africa Economic, Banking & Systemic Crisis Prediction

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]https://colab.research.google.com/github/OrkhanIsmayilov992/Africa-Economic-Banking-and-Systemic-Crisis/blob/main/africa-economic-banking-and-systemic-crisis-data.ipynb.ipynb)[https://colab.research.google.com/github/OrkhanIsmayilov992/Africa-Economic-Banking-and-Systemic-Crisis/blob/main/africa-economic-banking-and-systemic-crisis-data.ipynb.ipynb](https://colab.research.google.com/github/OrkhanIsmayilov992/Africa-Economic-Banking-and-Systemic-Crisis/blob/main/africa-economic-banking-and-systemic-crisis-data.ipynb.ipynb)

A machine learning project to predict **systemic economic crises** in African countries. The project analyzes macroeconomic indicators (exchange rate, inflation, sovereign debt defaults, etc.) for 13 African countries between 1860–2014 and compares four different classification models to assess crisis risk.

> 🚀 **Open in Google Colab:** [Launch Notebook in Colab](https://colab.research.google.com/github/OrkhanIsmayilov992/Africa-Economic-Banking-and-Systemic-Crisis/blob/main/africa-economic-banking-and-systemic-crisis-data.ipynb)  
> 📊 **Dataset:** [African Crises Dataset (Kaggle)](https://www.kaggle.com/datasets/chirin/africa-economic-banking-and-systemic-crisis-data)

---

## 📌 About the project

This notebook covers the following steps:

1. **Exploratory Data Analysis (EDA)** — checking for missing values, unique values, and variable distributions
2. **Data cleaning** — converting the `banking_crisis` column from text values (`crisis` / `no_crisis`) into 0/1 format
3. **Visualization**
   - Frequency plots for crisis types (systemic, currency, inflation, banking crises)
   - GDP-weighted default indicators by country
   - Exchange rate and inflation (CPI) trend charts for each country
   - Comparison of crisis frequency by independence status
4. **Feature selection and data split**
   - Target variable: `systemic_crisis` (more balanced class distribution — ~8-10% positive)
   - Features: `exch_usd`, `inflation_annual_cpi`, `gdp_weighted_default`
   - **Chronological split**: pre-1999 for training, 1999+ for testing (to avoid data leakage)
5. **Handling class imbalance** — SMOTE (Synthetic Minority Over-sampling)
6. **Model training** — four different models compared:
   - Logistic Regression
   - Decision Tree
   - Random Forest
   - XGBoost
7. **Evaluation** — comparing model performance using Accuracy, Precision, Recall, and F1-score

---

## 📈 Results

| Model | Recall (Class 1) | Notes |
|---|---|---|
| Logistic Regression | ~0.90 | High recall, but very low precision |
| Decision Tree | ~0.15 (Best F1: 0.169) | Most balanced model |
| Random Forest | ~0.25 | Good overall performance |
| XGBoost | ~0.21 | Captures non-linear patterns well |

**Recommended model:** Decision Tree — provides the best balance between Precision and Recall. If the priority is not missing any crises (Recall-focused), Logistic Regression may be more suitable, but it comes at the cost of many false positives.

---

## 🛠️ Tech Stack

- **Python** — pandas, numpy
- **Visualization** — matplotlib, seaborn
- **Machine Learning** — scikit-learn (Logistic Regression, Decision Tree, Random Forest), XGBoost
- **Class balancing** — imbalanced-learn (SMOTE)

---

## 🚀 Running the notebook

You can directly run this notebook in Google Colab without any local environment setup:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/OrkhanIsmayilov992/Africa-Economic-Banking-and-Systemic-Crisis/blob/main/africa-economic-banking-and-systemic-crisis-data.ipynb)

Alternatively, to run locally:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost imbalanced-learn
