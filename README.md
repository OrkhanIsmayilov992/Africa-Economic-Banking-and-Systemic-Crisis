# 🌍 Africa Economic, Banking & Systemic Crisis Prediction

A machine learning project to predict **systemic economic crises** in African countries. The project analyzes macroeconomic indicators (exchange rate, inflation, sovereign debt defaults, etc.) for 13 African countries between 1860–2014 and compares four different classification models to assess crisis risk.

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

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost imbalanced-learn
```

Download the dataset from [Kaggle](https://www.kaggle.com/datasets/chirin/africa-economic-banking-and-systemic-crisis-data), point to the `african_crises.csv` file path, then run the notebook cells in order.

---

## 📁 File Structure

```
├── africa_economic_banking_and_systemic_crisis_data.ipynb
└── README.md
```

---

## 📄 License

This project is for educational/research purposes. The dataset is licensed under [CC0: Public Domain](https://www.kaggle.com/datasets/chirin/africa-economic-banking-and-systemic-crisis-data).
