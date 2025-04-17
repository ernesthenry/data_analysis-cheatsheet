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

## 📈 Sample Visualizations

Below are examples of common visualizations you might create during your data analysis:

### Scatter Plot with Regression Line

```python
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np

# Sample data
np.random.seed(42)
x = np.random.normal(0, 1, 100)
y = 2*x + np.random.normal(0, 1, 100)

# Create scatter plot with regression line
plt.figure(figsize=(10, 6))
sns.regplot(x=x, y=y, scatter_kws={"color": "blue"}, line_kws={"color": "red"})
plt.title('Scatter Plot with Regression Line', fontsize=15)
plt.xlabel('X Variable', fontsize=12)
plt.ylabel('Y Variable', fontsize=12)
plt.grid(True, alpha=0.3)
plt.savefig('outputs/figures/scatter_regression.png', dpi=300)
plt.show()
```

![Scatter Plot with Regression Line](data:image/svg+xml;charset=utf-8,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 600 400'%3E%3Crect width='600' height='400' fill='white'/%3E%3Cg transform='translate(60, 20)'%3E%3C!-- Title --%3E%3Ctext x='240' y='20' font-family='Arial' font-size='16' text-anchor='middle' font-weight='bold'%3EScatter Plot with Regression Line%3C/text%3E%3C!-- Axes --%3E%3Cline x1='0' y1='320' x2='480' y2='320' stroke='black' stroke-width='2'/%3E%3Cline x1='0' y1='0' x2='0' y2='320' stroke='black' stroke-width='2'/%3E%3C!-- X-axis labels --%3E%3Ctext x='0' y='340' font-family='Arial' font-size='12' text-anchor='middle'%3E-3%3C/text%3E%3Ctext x='120' y='340' font-family='Arial' font-size='12' text-anchor='middle'%3E-2%3C/text%3E%3Ctext x='240' y='340' font-family='Arial' font-size='12' text-anchor='middle'%3E-1%3C/text%3E%3Ctext x='360' y='340' font-family='Arial' font-size='12' text-anchor='middle'%3E0%3C/text%3E%3Ctext x='480' y='340' font-family='Arial' font-size='12' text-anchor='middle'%3E1%3C/text%3E%3Ctext x='240' y='360' font-family='Arial' font-size='14' text-anchor='middle'%3EX Variable%3C/text%3E%3C!-- Y-axis labels --%3E%3Ctext x='-10' y='320' font-family='Arial' font-size='12' text-anchor='end'%3E-6%3C/text%3E%3Ctext x='-10' y='240' font-family='Arial' font-size='12' text-anchor='end'%3E-4%3C/text%3E%3Ctext x='-10' y='160' font-family='Arial' font-size='12' text-anchor='end'%3E-2%3C/text%3E%3Ctext x='-10' y='80' font-family='Arial' font-size='12' text-anchor='end'%3E0%3C/text%3E%3Ctext x='-10' y='0' font-family='Arial' font-size='12' text-anchor='end'%3E2%3C/text%3E%3Ctext transform='rotate(-90, -30, 160)' x='-30' y='160' font-family='Arial' font-size='14' text-anchor='middle'%3EY Variable%3C/text%3E%3C!-- Grid lines --%3E%3Cline x1='0' y1='240' x2='480' y2='240' stroke='gray' stroke-width='0.5' stroke-dasharray='5,5'/%3E%3Cline x1='0' y1='160' x2='480' y2='160' stroke='gray' stroke-width='0.5' stroke-dasharray='5,5'/%3E%3Cline x1='0' y1='80' x2='480' y2='80' stroke='gray' stroke-width='0.5' stroke-dasharray='5,5'/%3E%3Cline x1='120' y1='0' x2='120' y2='320' stroke='gray' stroke-width='0.5' stroke-dasharray='5,5'/%3E%3Cline x1='240' y1='0' x2='240' y2='320' stroke='gray' stroke-width='0.5' stroke-dasharray='5,5'/%3E%3Cline x1='360' y1='0' x2='360' y2='320' stroke='gray' stroke-width='0.5' stroke-dasharray='5,5'/%3E%3C!-- Regression line --%3E%3Cline x1='0' y1='240' x2='480' y2='80' stroke='red' stroke-width='2'/%3E%3C!-- Data points --%3E%3Ccircle cx='60' cy='260' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='100' cy='245' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='140' cy='230' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='170' cy='210' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='190' cy='200' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='220' cy='190' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='240' cy='180' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='260' cy='160' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='280' cy='150' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='290' cy='145' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='310' cy='140' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='320' cy='130' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='340' cy='125' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='350' cy='115' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='360' cy='110' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='380' cy='100' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='390' cy='90' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='400' cy='80' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='420' cy='70' r='4' fill='blue' opacity='0.7'/%3E%3Ccircle cx='440' cy='60' r='4' fill='blue' opacity='0.7'/%3E%3C/g%3E%3C/svg%3E)

### Histogram and KDE Plot

```python
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np

# Sample data
np.random.seed(42)
data = np.concatenate([np.random.normal(-2, 1, 200), np.random.normal(2, 1.5, 300)])

# Create histogram with KDE
plt.figure(figsize=(10, 6))
sns.histplot(data, kde=True, bins=30, color='skyblue', edgecolor='black')
plt.title('Histogram with KDE', fontsize=15)
plt.xlabel('Value', fontsize=12)
plt.ylabel('Frequency', fontsize=12)
plt.grid(True, alpha=0.3)
plt.savefig('outputs/figures/histogram_kde.png', dpi=300)
plt.show()
```

![Histogram with KDE](data:image/svg+xml;charset=utf-8,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 600 400'%3E%3Crect width='600' height='400' fill='white'/%3E%3Cg transform='translate(60, 20)'%3E%3C!-- Title --%3E%3Ctext x='240' y='20' font-family='Arial' font-size='16' text-anchor='middle' font-weight='bold'%3EHistogram with KDE%3C/text%3E%3C!-- Axes --%3E%3Cline x1='0' y1='320' x2='480' y2='320' stroke='black' stroke-width='2'/%3E%3Cline x1='0' y1='0' x2='0' y2='320' stroke='black' stroke-width='2'/%3E%3C!-- X-axis labels --%3E%3Ctext x='0' y='340' font-family='Arial' font-size='12' text-anchor='middle'%3E-6%3C/text%3E%3Ctext x='96' y='340' font-family='Arial' font-size='12' text-anchor='middle'%3E-4%3C/text%3E%3Ctext x='192' y='340' font-family='Arial' font-size='12' text-anchor='middle'%3E-2%3C/text%3E%3Ctext x='288' y='340' font-family='Arial' font-size='12' text-anchor='middle'%3E0%3C/text%3E%3Ctext x='384' y='340' font-family='Arial' font-size='12' text-anchor='middle'%3E2%3C/text%3E%3Ctext x='480' y='340' font-family='Arial' font-size='12' text-anchor='middle'%3E4%3C/text%3E%3Ctext x='240' y='360' font-family='Arial' font-size='14' text-anchor='middle'%3EValue%3C/text%3E%3C!-- Y-axis labels --%3E%3Ctext x='-10' y='320' font-family='Arial' font-size='12' text-anchor='end'%3E0%3C/text%3E%3Ctext x='-10' y='240' font-family='Arial' font-size='12' text-anchor='end'%3E20%3C/text%3E%3Ctext x='-10' y='160' font-family='Arial' font-size='12' text-anchor='end'%3E40%3C/text%3E%3Ctext x='-10' y='80' font-family='Arial' font-size='12' text-anchor='end'%3E60%3C/text%3E%3Ctext x='-10' y='0' font-family='Arial' font-size='12' text-anchor='end'%3E80%3C/text%3E%3Ctext transform='rotate(-90, -30, 160)' x='-30' y='160' font-family='Arial' font-size='14' text-anchor='middle'%3EFrequency%3C/text%3E%3C!-- Grid lines --%3E%3Cline x1='0' y1='240' x2='480' y2='240' stroke='gray' stroke-width='0.5' stroke-dasharray='5,5'/%3E%3Cline x1='0' y1='160' x2='480' y2='160' stroke='gray' stroke-width='0.5' stroke-dasharray='5,5'/%3E%3Cline x1='0' y1='80' x2='480' y2='80' stroke='gray' stroke-width='0.5' stroke-dasharray='5,5'/%3E%3Cline x1='96' y1='0' x2='96' y2='320' stroke='gray' stroke-width='0.5' stroke-dasharray='5,5'/%3E%3Cline x1='192' y1='0' x2='192' y2='320' stroke='gray' stroke-width='0.5' stroke-dasharray='5,5'/%3E%3Cline x1='288' y1='0' x2='288' y2='320' stroke='gray' stroke-width='0.5' stroke-dasharray='5,5'/%3E%3Cline x1='384' y1='0' x2='384' y2='320' stroke='gray' stroke-width='0.5' stroke-dasharray='5,5'/%3E%3C!-- Histogram bars --%3E%3Crect x='144' y='240' width='16' height='80' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='160' y='160' width='16' height='160' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='176' y='80' width='16' height='240' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='192' y='120' width='16' height='200' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='208' y='200' width='16' height='120' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='224' y='240' width='16' height='80' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='240' y='280' width='16' height='40' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='256' y='280' width='16' height='40' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='272' y='280' width='16' height='40' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='288' y='260' width='16' height='60' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='304' y='240' width='16' height='80' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='320' y='200' width='16' height='120' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='336' y='120' width='16' height='200' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='352' y='40' width='16' height='280' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='368' y='80' width='16' height='240' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='384' y='160' width='16' height='160' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='400' y='240' width='16' height='80' fill='skyblue' stroke='black' stroke-width='1'/%3E%3Crect x='416' y='280' width='16' height='40' fill='skyblue' stroke='black' stroke-width='1'/%3E%3C!-- KDE curve --%3E%3Cpath d='M0,320 C48,320 96,316 144,300 C168,290 192,240 216,170 C240,240 264,290 288,300 C336,316 384,320 480,320' fill='none' stroke='#ff7f0e' stroke-width='2'/%3E%3C/g%3E%3C/svg%3E)

### Heatmap for Correlation Matrix

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Generate sample data
np.random.seed(42)
data = {
    'feature1': np.random.normal(0, 1, 100),
    'feature2': np.random.normal(0, 1, 100),
    'feature3': np.random.normal(0, 1, 100),
    'feature4': np.random.normal(0, 1, 100)
}
df = pd.DataFrame(data)

# Create correlation matrix
corr_matrix = df.corr()

# Plot heatmap
plt.figure(figsize=(8, 6))
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm', vmin=-1, vmax=1, 
            linewidths=0.5, cbar_kws={"shrink": 0.8})
plt.title('Correlation Matrix Heatmap', fontsize=15)
plt.xticks(fontsize=10)
plt.yticks(fontsize=10)
plt.tight_layout()
plt.savefig('outputs/figures/correlation_heatmap.png', dpi=300)
plt.show()
```

![Correlation Heatmap](data:image/svg+xml;charset=utf-8,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 600 500'%3E%3Crect width='600' height='500' fill='white'/%3E%3Cg transform='translate(80, 60)'%3E%3C!-- Title --%3E%3Ctext x='200' y='-30' font-family='Arial' font-size='16' text-anchor='middle' font-weight='bold'%3ECorrelation Matrix Heatmap%3C/text%3E%3C!-- Heatmap cells --%3E%3Crect x='0' y='0' width='100' height='100' fill='#3783b7' stroke='white' stroke-width='1'/%3E%3Ctext x='50' y='50' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle' fill='white'%3E1.00%3C/text%3E%3Crect x='100' y='0' width='100' height='100' fill='#e3e9fc' stroke='white' stroke-width='1'/%3E%3Ctext x='150' y='50' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle'%3E0.06%3C/text%3E%3Crect x='200' y='0' width='100' height='100' fill='#fbd0d1' stroke='white' stroke-width='1'/%3E%3Ctext x='250' y='50' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle'%3E-0.12%3C/text%3E%3Crect x='300' y='0' width='100' height='100' fill='#f3dbdc' stroke='white' stroke-width='1'/%3E%3Ctext x='350' y='50' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle'%3E-0.08%3C/text%3E%3Crect x='0' y='100' width='100' height='100' fill='#e3e9fc' stroke='white' stroke-width='1'/%3E%3Ctext x='50' y='150' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle'%3E0.06%3C/text%3E%3Crect x='100' y='100' width='100' height='100' fill='#3783b7' stroke='white' stroke-width='1'/%3E%3Ctext x='150' y='150' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle' fill='white'%3E1.00%3C/text%3E%3Crect x='200' y='100' width='100' height='100' fill='#dbf0fb' stroke='white' stroke-width='1'/%3E%3Ctext x='250' y='150' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle'%3E0.09%3C/text%3E%3Crect x='300' y='100' width='100' height='100' fill='#e9e6fa' stroke='white' stroke-width='1'/%3E%3Ctext x='350' y='150' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle'%3E0.03%3C/text%3E%3Crect x='0' y='200' width='100' height='100' fill='#fbd0d1' stroke='white' stroke-width='1'/%3E%3Ctext x='50' y='250' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle'%3E-0.12%3C/text%3E%3Crect x='100' y='200' width='100' height='100' fill='#dbf0fb' stroke='white' stroke-width='1'/%3E%3Ctext x='150' y='250' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle'%3E0.09%3C/text%3E%3Crect x='200' y='200' width='100' height='100' fill='#3783b7' stroke='white' stroke-width='1'/%3E%3Ctext x='250' y='250' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle' fill='white'%3E1.00%3C/text%3E%3Crect x='300' y='200' width='100' height='100' fill='#f8d6d7' stroke='white' stroke-width='1'/%3E%3Ctext x='350' y='250' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle'%3E-0.10%3C/text%3E%3Crect x='0' y='300' width='100' height='100' fill='#f3dbdc' stroke='white' stroke-width='1'/%3E%3Ctext x='50' y='350' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle'%3E-0.08%3C/text%3E%3Crect x='100' y='300' width='100' height='100' fill='#e9e6fa' stroke='white' stroke-width='1'/%3E%3Ctext x='150' y='350' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle'%3E0.03%3C/text%3E%3Crect x='200' y='300' width='100' height='100' fill='#f8d6d7' stroke='white' stroke-width='1'/%3E%3Ctext x='250' y='350' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle'%3E-0.10%3C/text%3E%3Crect x='300' y='300' width='100' height='100' fill='#3783b7' stroke='white' stroke-width='1'/%3E%3Ctext x='350' y='350' font-family='Arial' font-size='12' text-anchor='middle' dominant-baseline='middle' fill='white'%3E1.00%3C/text%3E%3C!-- Axis labels --%3E%3Ctext x='50' y='420' font-family='Arial' font-size='12' text-anchor='middle'%3Efeature1%3C/text%3E%3Ctext x='150' y='420' font-family='Arial' font-size='12' text-anchor='middle'%3Efeature2%3C/text%3E%3Ctext x='250' y='420' font-family='Arial' font-size='12' text-anchor='middle'%3Efeature3%3C/text%3E%3Ctext x='350' y='420' font-family='Arial' font-size='12' text-anchor='middle'%3Efeature4%3C/text%3E%3Ctext transform='rotate(-90, -20, 50)' x='-20' y='50' font-family='Arial' font-size='12' text-anchor='middle'%3Efeature1%3C/text%3E%3Ctext transform='rotate(-90, -20, 150)' x='-20' y='150' font-family='Arial' font-size='12' text-anchor='middle'%3Efeature2%3C/text%3E%3Ctext transform='rotate(-90, -20, 250)' x='-20' y='250' font-family='Arial' font-size='12' text-anchor='middle'%3Efeature3%3C/text%3E%3Ctext transform='rotate(-90, -20, 350)' x='-20' y='350' font-family='Arial' font-size='12' text-anchor='middle'%3Efeature4%3C/text%3E%3C!-- Color bar --%3E%3Crect x='430' y='50' width='20' height='300' fill='url(%23gradient)'/%3E%3Ctext x='460' y='50' font-family='Arial' font-size='10' text-anchor='start'%3E1.0%3C/text%3E%3Ctext x='460' y='200' font-family='Arial' font-size='10' text-anchor='start'%3E0.0%3C/text%3E%3Ctext x='460' y='350' font-family='Arial' font-size='10' text-anchor='start'%3E-1.0%3C/text%3E%3Cdefs%3E%3ClinearGradient id='gradient' x1='0' y1='0' x2='0' y2='1'%3E%3Cstop offset='0' stop-color='%233783b7'/%3E%3Cstop offset='0.5' stop-color='%23ffffff'/%3E%3Cstop offset='1' stop-color='%23ca4b56'/%3E%3C/linearGradient%3E%3C/defs%3E%3C/g%3E%3C/svg%3E)

## 📊 Advanced Visualization Example: Pair Plot

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Generate sample dataset
np.random.seed(42)
data = {
    'length': np.random.normal(5, 1, 100),
    'width': np.random.normal(3, 0.5, 100),
    'height': np.random.normal(4, 0.7, 100),
    'weight': np.random.normal(10, 2, 100),
    'category': np.random.choice(['A', 'B', 'C'], 100)
}
df = pd.DataFrame(data)

# Create pair plot
plt.figure(figsize=(12, 10))
pair_plot = sns.pairplot(df, hue='category', palette='viridis')
plt.suptitle('Pair Plot of Features by Category', y=1.02, fontsize=16)
