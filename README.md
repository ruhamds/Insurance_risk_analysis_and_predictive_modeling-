Insurance Risk Analysis and Predictive Modeling 📈
Overview
This repository hosts the code and data pipeline for an insurance data analysis project using a dataset of policies from February 2014 to August 2015. The project aims to assess risk and profitability through Exploratory Data Analysis (EDA), statistical hypothesis testing, and data version control.

Key objectives include:

Calculating the Loss Ratio (TotalClaims / TotalPremium) and analyzing its variation by Province, VehicleType, and Gender.

Identifying distributions, outliers, and temporal trends in financial variables like TotalPremium and TotalClaims.

Testing hypotheses about risk drivers (e.g., Claim Frequency, Claim Severity) to inform segmentation strategies.

Establishing a reproducible data pipeline with Data Version Control (DVC) for regulatory compliance, a standard practice in regulated industries like finance and insurance.

Project Structure 📁
.github/workflows/ci.yml: GitHub Actions workflow for CI/CD (linting, testing).

eda_cleaning.ipynb: Python notebook for data cleaning, EDA, and eda_analysis.ipynb for visualizations.

data/: Directory for datasets (tracked by DVC).

notebooks/: Stores visualizations (e.g., loss_ratio_province.png) and statistics (e.g., descriptive_stats.csv).

requirements.txt: Python dependencies.

.dvc/: DVC configuration and data version metadata.

task-1/: Branch for Git setup, EDA, and statistical analysis.

task-2/: Branch for DVC implementation.

Setup ⚙️
Prerequisites
Git: For version control.

Python 3.9+: For analysis scripts.

DVC: For data version control.

PowerShell or Terminal: For running commands (PowerShell examples provided for Windows users).

Installation
Clone the Repository:

git clone https://github.com/ruhamds/Insurance_risk_analysis_and_predictive_modeling-.git
cd Insurance_Risk_Analysis_and_predictive_modeling

Checkout Branches:

Task 1:

git checkout task-1

Task 2:

git checkout task-2

Set Up Python Environment:

python -m venv venv
.\venv\Scripts\Activate.ps1 # On Windows
# source venv/bin/activate # On macOS/Linux
pip install -r requirements.txt

Install DVC & Initialize:

pip install dvc
dvc init

Configure DVC Local Storage:

mkdir C:\Insurance_Risk_Analysis_and_predictive_modeling/storage # Adjust path for your OS
dvc remote add -d localstorage C:\Insurance_Risk_Analysis_and_predictive_modeling/storage # Adjust path for your OS

Data 📊
Dataset: Insurance policies with columns like TotalPremium, TotalClaims, Province, VehicleType, Gender, TransactionMonth, PostalCode.

Source: Tracked by DVC in data/ (e.g., insurance_data.csv.dvc).

Key Metrics:

Loss Ratio: TotalClaims / TotalPremium.

Claim Frequency: Proportion of policies with TotalClaims > 0.

Claim Severity: Average TotalClaims for claims > 0.

Margin: TotalPremium - TotalClaims.

Task 1: Git, EDA, and Statistical Analysis 🧠
Git and GitHub
Repository: InsuranceEDA with branches task-1 and main.

Commits: Aim for at least 3 commits/day with descriptive messages (e.g., “Added data cleaning for zero premiums”).

CI/CD: GitHub Actions (ci.yml) runs flake8 linting and tests eda_cleaning.ipynb on pushes to task-1.

Exploratory Data Analysis (EDA)
Data Summarization: Descriptive statistics (mean, median) for TotalPremium, TotalClaims, etc.; checked data types.

Data Quality: Assessed missing values and zero premiums.

Univariate Analysis: Histograms for numerical variables, bar charts for categorical (e.g., Province).

Bivariate/Multivariate: Scatter plots of TotalPremium vs. TotalClaims by PostalCode, correlation matrices.

Trends: Analyzed claim frequency over TransactionMonth.

Outliers: Box plots for TotalClaims and CustomValueEstimate.

Visualizations Created:

Bar chart: Loss Ratio by Province.

Scatter plot: TotalPremium vs. TotalClaims by PostalCode.

Line plot: Claim frequency over time.

Statistical Thinking
Distributions: Identified skewness in TotalClaims (likely right-skewed).

Correlations: Analyzed relationships between financial variables.

Guiding Questions:

Overall Loss Ratio and variations by Province, VehicleType, Gender.

Outliers in TotalClaims and CustomValueEstimate.

Temporal trends in claim frequency/severity.

Vehicle makes/models with high/low claim amounts.

Task 2: Data Version Control (DVC) 💾
Purpose: Ensures reproducible data inputs for auditing and compliance, allowing any analysis or model result to be reproduced at any time.

Workflow
Initialized DVC:

dvc init

Added data:

dvc add data/insurance_data.csv

Configured local storage:

dvc remote add -d localstorage <your_storage_path>

Committed .dvc files to Git.

Pushed data to remote:

dvc push

Branch: task-2 for DVC setup and data versioning.

Pull Request: task-1 was merged into main via a Pull Request before starting task-2.

Usage ▶️
Run EDA:

python eda_cleaning.ipynb

Visualize:

eda_analysis.ipynb

Outputs: Visualizations and statistics will be saved in the notebooks/ directory.

Reproduce Data:

dvc pull

Retrieves versioned data from your local DVC storage (localstorage).

Check CI/CD:
Pushing to task-1 or task-2 branches will trigger GitHub Actions (see the "Actions" tab on the GitHub repository).

🚀 Key Features
Portfolio Loss Ratio Analysis (Current: 100.2%)

High-Risk Segment Identification:

Vehicle Types: Heavy Commercial (161.2% LR)

Geographic: Gauteng Province (116.4% LR)

Zero-Premium Policy Detection (381,634 cases, 38.2% of portfolio)

📊 Key Findings (Task 1)
Top Risk Drivers:

SUZUKI vehicles (625.3% Loss Ratio)

Zero-premium policies (38.2% of portfolio, impacting overall profitability)

Recommended Actions:

15% premium increase for commercial vehicles.

Blacklist highest-risk vehicle makes (e.g., Suzuki, JMC, Hyundai, Polarsun).

Author
Ruhama Israel
E-mail: ruheezrael@gmail.com