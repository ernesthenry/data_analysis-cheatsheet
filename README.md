# Data Analysis Project Setup Cheatsheet

This guide walks through setting up a complete data analysis environment from scratch, including virtual environment creation, installing necessary libraries, and pushing to GitHub.

## 🗂️ Step 1: Create a Project Folder

```bash
mkdir my-data-analysis-project
cd my-data-analysis-project
```

## 🐍 Step 2: Create and Activate a Virtual Environment

```bash
# Create virtual environment
python -m venv venv

# Activate (macOS/Linux)
source venv/bin/activate

# Activate (Windows)
venv\Scripts\activate
```

## 📦 Step 3: Install Required Libraries

```bash
# Install core data analysis packages
pip install pandas numpy matplotlib seaborn jupyter scikit-learn

# Optional: For working with Excel and SQL
pip install openpyxl sqlalchemy

# Freeze requirements
pip freeze > requirements.txt
```

## 📓 Step 4: Start Jupyter Notebook (Optional for Exploratory Analysis)

```bash
jupyter notebook
```

## 🧪 Step 5: Create Initial Project Structure

```bash
mkdir data notebooks scripts outputs
touch README.md .gitignore
```

Example `.gitignore` content:
```
venv/
__pycache__/
.ipynb_checkpoints/
outputs/
.DS_Store
*.pyc
```

## 🧬 Step 6: Initialize Git Repository

```bash
git init
git add .
git commit -m "Initial commit - project structure and environment setup"
```

## ☁️ Step 7: Push to GitHub

1. Go to GitHub and create a new repository
2. Push your local repository:

```bash
# Replace <username> and <repo-name> with your GitHub username and repository
git remote add origin https://github.com/<username>/<repo-name>.git
git branch -M main
git push -u origin main
```

## 🧭 Complete Project File Structure

```
my-data-analysis-project/
│
├── data/              # Raw data files
│   ├── raw/           # Original, immutable data
│   └── processed/     # Cleaned and processed data
│
├── notebooks/         # Jupyter notebooks for exploration and analysis
│
├── scripts/           # Python scripts for cleaning, analysis, etc.
│   ├── data_prep.py
│   └── analysis.py
│
├── outputs/           # Graphs, tables, reports
│   ├── figures/       # Generated visualizations
│   └── models/        # Trained models
│
├── README.md          # Project documentation
├── requirements.txt   # Package dependencies
└── .gitignore         # Files to exclude from version control
```

## 📊 Basic Data Analysis Workflow

1. **Data Collection**: Store raw data in the `data/raw/` directory
2. **Data Cleaning**: Create scripts in `scripts/` for data cleaning
3. **Exploratory Analysis**: Use Jupyter notebooks for exploration
4. **Feature Engineering**: Transform data for modeling
5. **Modeling**: Train and evaluate models
6. **Visualization**: Create visualizations for insights
7. **Reporting**: Document findings in notebooks or reports

## 📋 Common Data Analysis Commands

```python
# Import common libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load data
df = pd.read_csv('data/raw/dataset.csv')

# Examine data
df.head()
df.info()
df.describe()

# Data cleaning
df.dropna()  # or df.fillna(value)
df = df.drop_duplicates()

# Visualization
plt.figure(figsize=(10, 6))
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.savefig('outputs/figures/correlation_matrix.png')
```

## 🔄 Updating GitHub Repository

```bash
git add .
git commit -m "Add descriptive message about changes"
git push origin main
```