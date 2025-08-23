# 📊 Credit Scorecard Modeling – Lending Club Loan Data

## 📌 Project Overview
This repository contains a complete end‑to‑end workflow for **Credit Risk Scorecard Development** using **Lending Club** consumer loan data (2007–2015).  
The goal is to:
- Predict the **Probability of Default (PD)** for loan applicants
- Translate the statistical model into a **credit scorecard**
- Evaluate model performance with standard classification metrics (AUC, Gini, KS)
- Demonstrate cut‑off and approval rate analysis

The workflow follows international credit risk modeling practices, performing **Weight of Evidence (WoE)** binning, **Information Value (IV)** analysis, logistic regression modeling, and score scaling.

---

## 📂 Notebooks in this Repository

### 1. **Credit-Risk-Modeling-Preparation-With-Comments.ipynb**
**Purpose:** Data cleaning, preprocessing, and feature engineering.

Key steps:
- Load raw Lending Club data
- Preprocess continuous and categorical variables
- Handle missing values
- Apply **Weight of Evidence** (WoE) transformation
- Calculate **Information Value** (IV) for feature selection
- Perform **dummy variable creation** and **binning** for both categorical and continuous predictors
- Save **train/test** prepared datasets for modeling

---

### 2. **Credit-Risk-Modeling-PD-Model-With-Comments.ipynb**
**Purpose:** Build, evaluate, and deploy a PD (Probability of Default) logistic regression model.

Key steps:
- Load preprocessed datasets
- Select features and define reference categories
- Train **Logistic Regression** with statistical significance testing (**p-values**)
- Perform variable selection based on p-values
- Save the final **PD model** to disk
- Validate the model on a **hold-out test set**
- Evaluate performance using:
  - Confusion Matrix & Accuracy
  - ROC Curve & AUROC
  - Gini Coefficient
  - Kolmogorov–Smirnov (KS) statistic
- Build **Scorecard Scaling:**
  - Convert logistic regression coefficients to score points
  - Set minimum and maximum scores (e.g., 300–850)
  - Calculate applicant scores
  - Map scores back to PD values
- Cut‑off Analysis:
  - Approval and rejection rates for different score thresholds
  - Link score cut‑offs to business decisions

---

## 🗂 Data
- **Source:** Lending Club Loan Data (Kaggle – [Loan Data 2007–2015 by Wendy Kan](https://www.kaggle.com/wendykan/lending-club-loan-data))
- **Target Variable:** Binary default flag (`good_bad`)
  - `1` = Good loan (repaid)
  - `0` = Bad loan (default/charged off)
- **Features:**
  - Applicant profile (employment length, home ownership, income, state)
  - Loan details (term, purpose, funded amount, interest rate)
  - Credit history metrics (months since earliest credit, public records, revolving limits)

---

## ⚙️ Environment & Dependencies
**Python 3.x**  
Required libraries:
