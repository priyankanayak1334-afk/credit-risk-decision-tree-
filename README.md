# credit-risk-decision-tree-
### Automated Credit Risk Evaluation System Using Decision Trees

### 📌 Project Overview

This repository contains a decision-based Machine Learning system designed to evaluate risk and automate loan approvals for financial institutions. Built as part of **Phase: Decision-Based Learning (Day 17)**, this project demonstrates how to train a transparent, audit-ready **Decision Tree Classifier**, extract feature importances, handle overfitting through pre-pruning techniques, and generate clear visualizations to comply with modern explainable AI (XAI) mandates. 

### 🛠️ Tech Stack & Dependencies

* **Language:** Python 3.x
* **Environment:** Jupyter Notebook
* **Core Libraries:** 

  * scikit-learn (Modeling, Evaluation, Tree Visualisation)
  * pandas & numpy (Data Processing & Pipeline Engineering)
  * matplotlib & seaborn (Statistical Visualizations)

### 🚀 Workflow Execution Steps

### 1. Data Pipeline Design

We engineered a corporate-style risk dataset of 1,500 loan applicants using core banking attributes: 

* Credit_Score (Range: 400 - 850)
* Income (Range: $20,000 - $150,000)
* Debt_to_Income_Ratio (Range: 0.1 - 0.6)
* Loan_Amount (Range: $5,000 - $90,000)

### 2. Identifying & Fixing Overfitting

* **The Baseline Failure:** An unconstrained decision tree was intentionally trained first. It achieved **100% Training Accuracy** but suffered a massive drop on test data, proving that it memorised structural noise.
* **The Regularization Fix:** We applied pre-pruning hyperparameters (max_depth=3, min_samples_leaf=20) to eliminate over-indexing on anomalies, shrinking the variance gap down to an optimized, production-stable variance.

### 3. Tree Architecture Mapping

The logic-gate structure below represents the top decision layers utilized by the trained system to audit applicants: 

text

                      [ Credit_Score <= 645.5 ]
                             /          \
                           /              \
       [ Income <= 52000 ]                  [ Debt_to_Income_Ratio <= 0.42 ]
          /          \                         /          \
        /              \                     /              \
 [REJECT (Pure)]  [CS <= 690]         [APPROVED (Pure)]  [Income <= 72000]

Use code with caution.

### 4. Feature Importance Insights

By extracting the **Gini Importance** values, the system ranks key financial variables driving automated approval boundaries: 

* **Credit Score (~55%):** The primary root-node filter metric.
* **Income (~30%):** Secondary capacity check.
* **Debt-to-Income Ratio (~12%):** Critical leverage assessment boundary.
* **Loan Amount (~3%):** Marginal structural impact.

### 📊 Evaluation Metrics Matrix

The regularized model yields clean, high-precision performance suitable for banking compliance benchmarks: 

text

=== SYSTEM PERFORMANCE OVERVIEW REPORT ===
              precision    recall  f1-score   support

    REJECTED       0.94      0.92      0.93       142
    APPROVED       0.93      0.95      0.94       158

    accuracy                           0.94       300

Use code with caution.

### 📂 Repository Architecture

text

├── credit-risk-decision-tree/
│   ├── decision_tree_notebook.ipynb   # Documented Jupyter Notebook with step-by-step code
│   ├── README.md                      # Project documentation and summary report
│   └── assets/                        # Exported PNGs of the Tree layout and Feature Importance

Use code with caution.

### 💡 Industry Takeaway

Unlike complex "black-box" models, a regularized Decision Tree offers absolute **interpretability**. This structural transparency is critical for institutional risk alignment and regulatory compliance frameworks like the **Fair Credit Reporting Act (FCRA)**.
