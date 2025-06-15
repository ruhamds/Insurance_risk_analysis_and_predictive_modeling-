Insurance Risk Analysis and Predictive Modeling 📈
Overview
This repository contains code and data pipelines for analyzing insurance policies from February 2014 to August 2015. The project assesses risk and profitability through Exploratory Data Analysis (EDA), statistical hypothesis testing, and a reproducible data pipeline using Data Version Control (DVC). Key objectives:

Calculate Loss Ratio (TotalClaims / TotalPremium) and analyze variations by Province, VehicleType, and Gender.
Identify distributions, outliers, and temporal trends in TotalPremium and TotalClaims.
Test hypotheses about risk drivers (e.g., Claim Frequency, Claim Severity) for segmentation strategies.
Ensure reproducibility for regulatory compliance in insurance.

Author: Ruhama Israel (ruheezrael@gmail.com)
Project Structure 📁

.github/workflows/ci.yml: GitHub Actions for CI/CD (linting, testing).
notebooks/eda_cleaning.ipynb: Jupyter Notebook for data cleaning and EDA.
notebooks/eda_analysis.ipynb: Notebook for visualizations and statistical analysis.
data/: Datasets tracked by DVC (e.g., insurance_data.csv.dvc).
notebooks/: Stores outputs (e.g., loss_ratio_province.png, descriptive_stats.csv).
requirements.txt: Python dependencies.
.dvc/: DVC configuration and metadata.
task-1: Branch for Git setup and EDA.
task-2: Branch for DVC implementation.

Setup ⚙️
Prerequisites

Git
Python 3.9+
DVC
PowerShell (Windows) or Terminal (macOS/Linux)

Installation

Clone Repository:git clone https://github.com/ruhamds/Insurance_risk_analysis_and_predictive_modeling-.git
cd Insurance_Risk_Analysis_and_predictive_modeling


Checkout Branches:
Task 1: git checkout task-1
Task 2: git checkout task-2


Set Up Python Environment:python -m venv venv
.\venv\Scripts\Activate.ps1
pip install -r requirements.txt


Install and Initialize DVC:pip install dvc
dvc init


Configure DVC Storage:mkdir C:\Insurance_Risk_Analysis_and_predictive_modeling\storage
dvc remote add -d localstorage C:\Insurance_Risk_Analysis_and_predictive_modeling\storage



Data 📊

Dataset: Insurance policies with columns: TotalPremium, TotalClaims, Province, VehicleType, Gender, TransactionMonth, PostalCode.
Source: Tracked in data/ via DVC.
Metrics:
Loss Ratio: TotalClaims / TotalPremium
Claim Frequency: Proportion of policies with TotalClaims > 0
Claim Severity: Average TotalClaims for claims > 0
Margin: TotalPremium - TotalClaims



Task 1: Git, EDA, and Statistical Analysis 🧠
Git and GitHub

Repository: Insurance_Risk_Analysis_and_predictive_modeling with task-1 and main branches.
Commits: 3+/day with descriptive messages (e.g., “Added zero premium handling”).
CI/CD: GitHub Actions (ci.yml) runs flake8 and tests notebooks on task-1 pushes.

EDA

Summarization: Descriptive stats for TotalPremium, TotalClaims; verified data types.
Quality: Handled missing values and 381,634 zero-premium policies (38.2% of portfolio).
Univariate: Histograms (TotalClaims), bar charts (Province).
Bivariate: Scatter plots (TotalPremium vs. TotalClaims by PostalCode), correlation matrices.
Trends: Claim frequency over TransactionMonth.
Outliers: Box plots for TotalClaims, CustomValueEstimate.
Visualizations:
Bar Chart: Loss Ratio by Province (e.g., Gauteng: 116.4%).
Scatter Plot: TotalPremium vs. TotalClaims by PostalCode.
Line Plot: Claim frequency over time.



Statistical Thinking

Distributions: TotalClaims likely right-skewed.
Correlations: Analyzed financial variable relationships.
Insights:
Portfolio Loss Ratio: 100.2%.
High-risk: Heavy Commercial vehicles (161.2% LR), SUZUKI (625.3% LR).
Zero-premium policies impact profitability.



Task 2: Data Version Control (DVC) 💾

Purpose: Ensures reproducible data for auditing.
Workflow:
Initialized: dvc init
Added data: dvc add data/insurance_data.csv
Configured storage: dvc remote add -d localstorage
Committed .dvc files to Git.
Pushed data: dvc push


Branch: task-2
Pull Request: Merged task-1 to main via PR.

Usage ▶️

Run EDA:jupyter notebook notebooks/eda_cleaning.ipynb


Visualize:jupyter notebook notebooks/eda_analysis.ipynb


Outputs saved in notebooks/.


Reproduce Data:dvc pull


Check CI/CD: Push to task-1/task-2 triggers GitHub Actions.

Key Findings 🚀

Portfolio Loss Ratio: 100.2%, indicating break-even.
High-Risk Segments:
Vehicle Types: Heavy Commercial (161.2% LR).
Geographic: Gauteng (116.4% LR).
Makes: SUZUKI (625.3% LR), JMC, Hyundai, Polarsun.


Zero-Premium Policies: 381,634 cases (38.2%), reducing profitability.
Recommendations:
15% premium increase for commercial vehicles.
Blacklist high-risk vehicle makes (e.g., SUZUKI).



Contributing 🤝

Work on task-1 or task-2.
Commit with descriptive messages:git add .
git commit -m "Added visualization for Loss Ratio"
git push origin task-1


Create pull requests to main.

References 📚

Pandas
DVC
GitHub
Loss Ratio


