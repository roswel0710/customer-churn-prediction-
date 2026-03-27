# 📊 Customer Churn Prediction | Machine Learning (Python & Scikit-learn)

[![Python](https://img.shields.io/badge/Python-3.10-blue)](https://www.python.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--Learn-ML-orange)](https://scikit-learn.org/)
[![Model](https://img.shields.io/badge/Model-Logistic%20Regression-green)](https://scikit-learn.org/stable/modules/linear_model.html)
[![ROC-AUC](https://img.shields.io/badge/AUC-0.89-success)](#)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)

---


## 📌 Project Overview

This project demonstrates an **end-to-end machine learning workflow** to predict customer churn in an e-commerce environment.

The focus is not just model building, but:
- Applying **structured data analysis**
- Handling **class imbalance effectively**
- Aligning model performance with **business objectives**

---

## 🎯 Business Objective

To build a churn prediction model that:
- Identifies **high-risk customers early**
- Minimizes missed churners (**recall-focused**)  
- Supports **data-driven retention strategies**

---
## 📦 Dataset

The dataset was sourced from **Kaggle** and contains **5,630 customer records** with behavioral, transactional, and demographic features.

- Customer behavior: OrderCount, CouponUsed, HourSpendOnApp  
- Engagement: Tenure, SatisfactionScore  
- Transaction: CashbackAmount, Payment Mode  
- Customer profile: Gender, Marital Status, City Tier

---
## 🧩 Analytical Workflow

### 🔹 Data Understanding & EDA
- Identified **class imbalance (~17% churn)**
- Key patterns:
  - Complaints strongly linked to churn
  - Majority churn occurs in early tenure

### 🔹 Data Cleaning
- Missing values handled using:
  - **Median** → skewed features (OrderCount, CouponUsed, etc.)
  - **Mean** → stable features (HourSpendOnApp)
- Ensured fully clean dataset before modeling

### 🔹 Feature Engineering
- One-hot encoding for categorical variables
- Removed non-informative feature (`CustomerID`)
- Feature scaling using `StandardScaler`

### 🔹 Model Development
- Logistic Regression used as baseline model
- Implemented using **Pipeline**:
  - Prevents data leakage
  - Ensures consistent preprocessing

### 🔹 Class Imbalance Handling
- Applied `class_weight='balanced'`
- Improved model sensitivity toward churn class

### 🔹 Threshold Optimization
- Default threshold: **0.5**
- Optimized threshold: **0.3**

Result:
- Significant improvement in **recall (churn detection)**

---

## 📈 Model Performance

| Metric | Before | After Optimization |
|------|--------|------------------|
| Accuracy | ~91% | ~83% |
| Recall (Churn) | 58% | **90%** |
| Precision | 86% | 34% |
| ROC-AUC | — | **0.89** |

---

## 📊 Model Evaluation Logic

- Accuracy alone was **misleading due to imbalance**
- Focus shifted to:
  - **Recall → capturing churners**
  - **ROC-AUC → overall model quality**
- Trade-off accepted:
  - Higher recall ✔️  
  - Lower precision ⚠️  

---

## 🔍 Key Drivers of Churn

From model coefficients:

- 📌 **Complain** → strongest predictor  
- 📉 **Low Tenure** → early churn risk  
- 🚚 **Warehouse-to-home distance** → service impact  
- 💳 **Cash on Delivery** → higher churn tendency  
- 👤 **Single customers** → higher churn probability  

---

## 💼 Business Impact

- Enables **early identification of at-risk customers**
- Supports **targeted retention campaigns**
- Improves **customer lifetime value**
- Helps reduce **revenue loss due to churn**

---

## 🧠 Technical Highlights

- End-to-end ML pipeline (EDA → Cleaning → Modeling → Evaluation)
- Proper handling of **missing data**
- Class imbalance solution using **class weights**
- **Threshold tuning based on business needs**
- Use of **ROC-AUC for imbalanced evaluation**
- Feature importance using **model coefficients**

---

## 📂 Repository Structure

```text
customer-churn-prediction/
├── notebook/
│   └── Final_Churn_Project.ipynb
├── data/
│   └── dataset.csv
└── README.md
