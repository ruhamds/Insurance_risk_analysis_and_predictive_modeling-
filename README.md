
## 🧠 Risk Modeling & Pricing Optimization Project

### Overview
This repository covers the complete pipeline for building a risk-based insurance pricing system. It spans data exploration, hypothesis testing, version control, reproducible workflows, and predictive modeling using Python, GitHub Actions, and DVC.

---

### 🔧 Task 1: EDA & GitHub Setup
- Initialized Git repo with CI/CD via GitHub Actions.
- Created `task-1` branch for structured versioning.
- Performed Exploratory Data Analysis:
  - Loss Ratio insights by Province, Gender, VehicleType.
  - Detected outliers in `TotalClaims` and `CustomValueEstimate`.
  - Identified temporal and geographic trends.
- Delivered 3 high-quality visualizations to communicate key findings.

---

### 📦 Task 2: Data Versioning with DVC
- Installed and configured DVC with local remote storage.
- Tracked datasets using `dvc add` and linked them to Git commits.
- Ensured reproducibility by pushing data artifacts and .dvc files.
- Created `task-2` branch, merged Task 1 using PR.

---

### 📊 Task 3: Statistical Risk Hypotheses
- Conducted A/B tests on:
  - Gender-based and region-based risk differences.
  - Profit margin variation by ZipCode.
- Rejected/retained null hypotheses using t-tests and chi-squared tests.
- Interpreted findings for business: e.g., higher claim severity in Gauteng may require premium adjustments.

---

### 🤖 Task 4: Predictive Modeling
- Built ML models for:
  - Claim Severity (regression for `TotalClaims` on claim > 0).
  - Premium Optimization (regression for `CalculatedPremium`).
  - Claim Probability (classification).
- Models used: Linear Regression, Decision Trees, Random Forest, XGBoost.
- Evaluation Metrics: RMSE, R², AUC-ROC, MAE.
- Applied SHAP for interpretability and feature attribution.

---

### 📁 Project Structure
```bash
├── data/                  # Raw & versioned datasets (tracked via DVC)
├── notebooks/             # Jupyter notebooks for EDA, modeling, hypothesis
├── src/                   # Modular Python scripts for preprocessing & training
├── .github/workflows/     # GitHub Actions CI/CD definitions
├── dvc.yaml               # DVC pipeline stages
└── README.md              # Project overview and documentation
```

---

### 🚀 Getting Started
Clone the repo, install dependencies, and activate DVC:
```bash
pip install -r requirements.txt
dvc pull
```

---
