# 🏦 Loan Default Risk Prediction & Analysis

## 📌 Overview
This project focuses on predicting loan default risk and understanding the key factors that influence it using Machine Learning and Power BI.

The objective is to help financial institutions identify high-risk customers and make better lending decisions.

---

## 💼 Business Problem
Loan defaults can lead to significant financial losses. The challenge is to accurately identify risky customers in a **highly imbalanced dataset (~8% defaults)**.

Traditional accuracy-based models fail in such cases, making it important to focus on metrics like recall and ROC-AUC.

---

## 📂 Dataset
The dataset consists of **300K+ customer records** across two files:

- **Application Data** → Customer demographics & financial details  
- **Previous Loan Data** → Historical loan behavior  

### 🎯 Target Variable
- `TARGET = 1` → Default  
- `TARGET = 0` → No Default  

---

## 🧹 Data Preparation

- Selected relevant features from large datasets  
- Handled missing values:
  - Numerical → Median imputation  
  - Categorical → "Unknown"  
- Removed invalid categories (e.g., XNA)  
- Fixed anomalies (e.g., DAYS_EMPLOYED issue)  
- Treated outliers (income capping)

---

## ⚙️ Feature Engineering

Created meaningful features to improve model performance:

- **ANNUITY_BURDEN** = Annuity / Income  
- **INCOME_TO_CREDIT_RATIO** = Income / Credit  
- **Employment duration (years)**  
- **Previous loan aggregation**:
  - Average, max, total credit  
  - Number of previous applications  

---

## 🤖 Modeling

### 1. Logistic Regression (Final Model)
- Used `class_weight='balanced'` to handle imbalance  
- Applied feature scaling  
- Performed threshold tuning  

### 2. Random Forest
- Tuned parameters (max_depth, min_samples_leaf)  
- Compared performance with Logistic Regression  

---

## 📊 Model Performance

| Metric | Value |
|------|------|
| Recall (Default Class) | ~0.68 |
| Precision | ~0.16 |
| ROC-AUC | ~0.74 |

### 🎯 Key Focus
- Maximizing **recall** to detect defaulters  
- Maintaining reasonable precision  

---

## 📈 Key Insights

- External credit scores are the strongest predictors of default  
- Higher financial burden significantly increases risk  
- Employment stability reduces default probability  
- Default risk declines after 5–10 years of employment  
- Younger customers show higher default tendencies  
- Default risk is driven by multiple interacting factors  

---

## 📊 Dashboard

A Power BI dashboard was built to visualize risk patterns and business insights.

<img width="1280" height="721" alt="dashboard" src="https://github.com/user-attachments/assets/d0c80f98-efeb-443e-af47-ec9ae1426a75" />

---

## 💼 Business Recommendations

- Focus on customers with high financial burden  
- Monitor customers with unstable employment  
- Use multi-factor risk assessment instead of relying on a single variable  
- Adjust lending strategy based on risk segments  

---

## 🚀 Future Improvements

- Implement XGBoost for performance improvement  
- Apply SMOTE for advanced imbalance handling  
- Deploy model using Flask/Streamlit  
- Build real-time risk scoring system  

---

## 🛠️ Tech Stack
- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Scikit-learn
- Power BI
- Jupyter Notebook

---

## 👤 Author
**Bharat Lalwani**
[LinkedIn](https://www.linkedin.com/in/bharatlalwani-analytics) • [GitHub](https://github.com/bharatlalwani-analytics)
