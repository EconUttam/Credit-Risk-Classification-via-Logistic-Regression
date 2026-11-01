# Credit Risk Classification via Logistic Regression

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/EconUttam/Credit-Risk-Classification-via-Logistic-Regression/blob/main/Credit_Risk_Modelling_Project.ipynb)

## 📌 Project Overview
This repository contains a complete empirical credit risk modeling framework built on the **South German Credit Dataset** (UCI Machine Learning Repository)[cite: 65]. The project evaluates applicant risk profiles using **Logistic Regression**, incorporating exploratory data analysis (EDA)[cite: 66, 68], categorical feature encoding[cite: 65, 67], validation-based decision threshold selection[cite: 66, 74], and statistical inference on odds ratios[cite: 65, 66].

Target Variable: `default_risk` (1 = Bad Risk, 0 = Good Risk)[cite: 67]

---

## 📊 Key Highlights & Results

### 1. Statistical Inference Highlights
Model estimated via `statsmodels` ($N = 800$, McFadden Pseudo-$R^2 = 0.1427$)[cite: 73, 74]:
- **Loan Duration**: Statistically significant positive association with default risk ($OR = 1.037, p < 0.001$). Each additional month increases odds of bad risk by ~3.7%[cite: 66, 74].
- **Credit History & Savings**: Favorable history codes and higher savings tiers significantly lower the odds of bad-risk classification ($p < 0.05$)[cite: 66, 73, 74].
- **Credit Amount & Age**: Not statistically significant at the 5% level conditional on other included variables[cite: 70, 74].

### 2. Held-Out Test Set Performance ($N = 200$)
To address class imbalance (70% Good / 30% Bad)[cite: 67, 68], a custom decision threshold of **0.34** was selected on validation data (achieving $\ge 50\%$ recall target)[cite: 66, 74]:

| Metric | Baseline (Threshold 0.50) | Final Model (Threshold 0.34) | Notes / Interpretation |
| :--- | :---: | :---: | :--- |
| **Accuracy** | 73.0% | **67.0%** | Expected drop from prioritizing bad-risk detection[cite: 66, 75] |
| **Precision (Bad Risk)** | 60.7% | **45.6%** | Share of flagged applicants who were actual bad risk[cite: 72, 75] |
| **Recall (Bad Risk)** | 28.3% | **51.7%** | **+82.7% increase** in identifying risky applicants[cite: 72, 75] |
| **F1-Score** | 38.6% | **48.4%** | Overall balance of precision and recall[cite: 72, 75] |
| **ROC-AUC** | 0.698 | **0.698** | Rank discrimination across thresholds[cite: 66, 75] |

---

## 📁 Repository Structure

```text
├── Credit_Risk_Modelling_Project.ipynb    # Main Python Jupyter notebook (executed in Colab)
├── credit risk.pdf                        # Comprehensive Project Report
├── credit_risk_executive_summary.pdf      # 1-Page Executive Summary PDF
├── README.md                              # Repository documentation
└── LICENSE                                # Project license
