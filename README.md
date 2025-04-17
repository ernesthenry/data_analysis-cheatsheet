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

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 400">
  <rect width="600" height="400" fill="white"/>
  <g transform="translate(60, 20)">
    <!-- Title -->
    <text x="240" y="20" font-family="Arial" font-size="16" text-anchor="middle" font-weight="bold">Scatter Plot with Regression Line</text>
    <!-- Axes -->
    <line x1="0" y1="320" x2="480" y2="320" stroke="black" stroke-width="2"/>
    <line x1="0" y1="0" x2="0" y2="320" stroke="black" stroke-width="2"/>
    <!-- X-axis labels -->
    <text x="0" y="340" font-family="Arial" font-size="12" text-anchor="middle">-3</text>
    <text x="120" y="340" font-family="Arial" font-size="12" text-anchor="middle">-2</text>
    <text x="240" y="340" font-family="Arial" font-size="12" text-anchor="middle">-1</text>
    <text x="360" y="340" font-family="Arial" font-size="12" text-anchor="middle">0</text>
    <text x="480" y="340" font-family="Arial" font-size="12" text-anchor="middle">1</text>
    <text x="240" y="360" font-family="Arial" font-size="14" text-anchor="middle">X Variable</text>
    <!-- Y-axis labels -->
    <text x="-10" y="320" font-family="Arial" font-size="12" text-anchor="end">-6</text>
    <text x="-10" y="240" font-family="Arial" font-size="12" text-anchor="end">-4</text>
    <text x="-10" y="160" font-family="Arial" font-size="12" text-anchor="end">-2</text>
    <text x="-10" y="80" font-family="Arial" font-size="12" text-anchor="end">0</text>
    <text x="-10" y="0" font-family="Arial" font-size="12" text-anchor="end">2</text>
    <text transform="rotate(-90, -30, 160)" x="-30" y="160" font-family="Arial" font-size="14" text-anchor="middle">Y Variable</text>
    <!-- Grid lines -->
    <line x1="0" y1="240" x2="480" y2="240" stroke="gray" stroke-width="0.5" stroke-dasharray="5,5"/>
    <line x1="0" y1="160" x2="480" y2="160" stroke="gray" stroke-width="0.5" stroke-dasharray="5,5"/>
    <line x1="0" y1="80" x2="480" y2="80" stroke="gray" stroke-width="0.5" stroke-dasharray="5,5"/>
    <line x1="120" y1="0" x2="120" y2="320" stroke="gray" stroke-width="0.5" stroke-dasharray="5,5"/>
    <line x1="240" y1="0" x2="240" y2="320" stroke="gray" stroke-width="0.5" stroke-dasharray="5,5"/>
    <line x1="360" y1="0" x2="360" y2="320" stroke="gray" stroke-width="0.5" stroke-dasharray="5,5"/>
    <!-- Regression line -->
    <line x1="0" y1="240" x2="480" y2="80" stroke="red" stroke-width="2"/>
    <!-- Data points -->
    <circle cx="60" cy="260" r="4" fill="blue" opacity="0.7"/>
    <circle cx="100" cy="245" r="4" fill="blue" opacity="0.7"/>
    <circle cx="140" cy="230" r="4" fill="blue" opacity="0.7"/>
    <circle cx="170" cy="210" r="4" fill="blue" opacity="0.7"/>
    <circle cx="190" cy="200" r="4" fill="blue" opacity="0.7"/>
    <circle cx="220" cy="190" r="4" fill="blue" opacity="0.7"/>
    <circle cx="240" cy="180" r="4" fill="blue" opacity="0.7"/>
    <circle cx="260" cy="160" r="4" fill="blue" opacity="0.7"/>
    <circle cx="280" cy="150" r="4" fill="blue" opacity="0.7"/>
    <circle cx="290" cy="145" r="4" fill="blue" opacity="0.7"/>
    <circle cx="310" cy="140" r="4" fill="blue" opacity="0.7"/>
    <circle cx="320" cy="130" r="4" fill="blue" opacity="0.7"/>
    <circle cx="340" cy="125" r="4" fill="blue" opacity="0.7"/>
    <circle cx="350" cy="115" r="4" fill="blue" opacity="0.7"/>
    <circle cx="360" cy="110" r="4" fill="blue" opacity="0.7"/>
    <circle cx="380" cy="100" r="4" fill="blue" opacity="0.7"/>
    <circle cx="390" cy="90" r="4" fill="blue" opacity="0.7"/>
    <circle cx="400" cy="80" r="4" fill="blue" opacity="0.7"/>
    <circle cx="420" cy="70" r="4" fill="blue" opacity="0.7"/>
    <circle cx="440" cy="60" r="4" fill="blue" opacity="0.7"/>
  </g>
</svg>

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

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 400">
  <rect width="600" height="400" fill="white"/>
  <g transform="translate(60, 20)">
    <!-- Title -->
    <text x="240" y="20" font-family="Arial" font-size="16" text-anchor="middle" font-weight="bold">Histogram with KDE</text>
    <!-- Axes -->
    <line x1="0" y1="320" x2="480" y2="320" stroke="black" stroke-width="2"/>
    <line x1="0" y1="0" x2="0" y2="320" stroke="black" stroke-width="2"/>
    <!-- X-axis labels -->
    <text x="0" y="340" font-family="Arial" font-size="12" text-anchor="middle">-6</text>
    <text x="96" y="340" font-family="Arial" font-size="12" text-anchor="middle">-4</text>
    <text x="192" y="340" font-family="Arial" font-size="12" text-anchor="middle">-2</text>
    <text x="288" y="340" font-family="Arial" font-size="12" text-anchor="middle">0</text>
    <text x="384" y="340" font-family="Arial" font-size="12" text-anchor="middle">2</text>
    <text x="480" y="340" font-family="Arial" font-size="12" text-anchor="middle">4</text>
    <text x="240" y="360" font-family="Arial" font-size="14" text-anchor="middle">Value</text>
    <!-- Y-axis labels -->
    <text x="-10" y="320" font-family="Arial" font-size="12" text-anchor="end">0</text>
    <text x="-10" y="240" font-family="Arial" font-size="12" text-anchor="end">20</text>
    <text x="-10" y="160" font-family="Arial" font-size="12" text-anchor="end">40</text>
    <text x="-10" y="80" font-family="Arial" font-size="12" text-anchor="end">60</text>
    <text x="-10" y="0" font-family="Arial" font-size="12" text-anchor="end">80</text>
    <text transform="rotate(-90, -30, 160)" x="-30" y="160" font-family="Arial" font-size="14" text-anchor="middle">Frequency</text>
    <!-- Grid lines -->
    <line x1="0" y1="240" x2="480" y2="240" stroke="gray" stroke-width="0.5" stroke-dasharray="5,5"/>
    <line x1="0" y1="160" x2="480" y2="160" stroke="gray" stroke-width="0.5" stroke-dasharray="5,5"/>
    <line x1="0" y1="80" x2="480" y2="80" stroke="gray" stroke-width="0.5" stroke-dasharray="5,5"/>
    <line x1="96" y1="0" x2="96" y2="320" stroke="gray" stroke-width="0.5" stroke-dasharray="5,5"/>
    <line x1="192" y1="0" x2="192" y2="320" stroke="gray" stroke-width="0.5" stroke-dasharray="5,5"/>
    <line x1="288" y1="0" x2="288" y2="320" stroke="gray" stroke-width="0.5" stroke-dasharray="5,5"/>
    <line x1="384" y1="0" x2="384" y2="320" stroke="gray" stroke-width="0.5" stroke-dasharray="5,5"/>
    <!-- Histogram bars -->
    <rect x="144" y="240" width="16" height="80" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="160" y="160" width="16" height="160" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="176" y="80" width="16" height="240" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="192" y="120" width="16" height="200" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="208" y="200" width="16" height="120" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="224" y="240" width="16" height="80" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="240" y="280" width="16" height="40" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="256" y="280" width="16" height="40" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="272" y="280" width="16" height="40" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="288" y="260" width="16" height="60" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="304" y="240" width="16" height="80" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="320" y="200" width="16" height="120" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="336" y="120" width="16" height="200" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="352" y="40" width="16" height="280" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="368" y="80" width="16" height="240" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="384" y="160" width="16" height="160" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="400" y="240" width="16" height="80" fill="skyblue" stroke="black" stroke-width="1"/>
    <rect x="416" y="280" width="16" height="40" fill="skyblue" stroke="black" stroke-width="1"/>
    <!-- KDE curve -->
    <path d="M0,320 C48,320 96,316 144,300 C168,290 192,240 216,170 C240,240 264,290 288,300 C336,316 384,320 480,320" fill="none" stroke="#ff7f0e" stroke-width="2"/>
  </g>
</svg>

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

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 500">
  <rect width="600" height="500" fill="white"/>
  <g transform="translate(80, 60)">
    <!-- Title -->
    <text x="200" y="-30" font-family="Arial" font-size="16" text-anchor="middle" font-weight="bold">Correlation Matrix Heatmap</text>
    <!-- Heatmap cells -->
    <rect x="0" y="0" width="100" height="100" fill="#3783b7" stroke="white" stroke-width="1"/>
    <text x="50" y="50" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle" fill="white">1.00</text>
    <rect x="100" y="0" width="100" height="100" fill="#e3e9fc" stroke="white" stroke-width="1"/>
    <text x="150" y="50" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle">0.06</text>
    <rect x="200" y="0" width="100" height="100" fill="#fbd0d1" stroke="white" stroke-width="1"/>
    <text x="250" y="50" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle">-0.12</text>
    <rect x="300" y="0" width="100" height="100" fill="#f3dbdc" stroke="white" stroke-width="1"/>
    <text x="350" y="50" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle">-0.08</text>
    <rect x="0" y="100" width="100" height="100" fill="#e3e9fc" stroke="white" stroke-width="1"/>
    <text x="50" y="150" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle">0.06</text>
    <rect x="100" y="100" width="100" height="100" fill="#3783b7" stroke="white" stroke-width="1"/>
    <text x="150" y="150" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle" fill="white">1.00</text>
    <rect x="200" y="100" width="100" height="100" fill="#dbf0fb" stroke="white" stroke-width="1"/>
    <text x="250" y="150" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle">0.09</text>
    <rect x="300" y="100" width="100" height="100" fill="#e9e6fa" stroke="white" stroke-width="1"/>
    <text x="350" y="150" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle">0.03</text>
    <rect x="0" y="200" width="100" height="100" fill="#fbd0d1" stroke="white" stroke-width="1"/>
    <text x="50" y="250" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle">-0.12</text>
    <rect x="100" y="200" width="100" height="100" fill="#dbf0fb" stroke="white" stroke-width="1"/>
    <text x="150" y="250" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle">0.09</text>
    <rect x="200" y="200" width="100" height="100" fill="#3783b7" stroke="white" stroke-width="1"/>
    <text x="250" y="250" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle" fill="white">1.00</text>
    <rect x="300" y="200" width="100" height="100" fill="#f8d6d7" stroke="white" stroke-width="1"/>
    <text x="350" y="250" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle">-0.10</text>
    <rect x="0" y="300" width="100" height="100" fill="#f3dbdc" stroke="white" stroke-width="1"/>
    <text x="50" y="350" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle">-0.08</text>
    <rect x="100" y="300" width="100" height="100" fill="#e9e6fa" stroke="white" stroke-width="1"/>
    <text x="150" y="350" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle">0.03</text>
    <rect x="200" y="300" width="100" height="100" fill="#f8d6d7" stroke="white" stroke-width="1"/>
    <text x="250" y="350" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle">-0.10</text>
    <rect x="300" y="300" width="100" height="100" fill="#3783b7" stroke="white" stroke-width="1"/>
    <text x="350" y="350" font-family="Arial" font-size="12" text-anchor="middle" dominant-baseline="middle" fill="white">1.00</text>
    <!-- Axis labels -->
    <text x="50" y="420" font-family="Arial" font-size="12" text-anchor="middle">feature1</text>
    <text x="150" y="420" font-family="Arial" font-size="12" text-anchor="middle">feature2</text>
    <text x="250" y="420" font-family="Arial" font-size="12" text-anchor="middle">feature3</text>
    <text x="350" y="420" font-family="Arial" font-size="12" text-anchor="middle">feature4</text>
    <text transform="rotate(-90, -20, 50)" x="-20" y="50" font-family="Arial" font-size="12" text-anchor="middle">feature1</text>
    <text transform="rotate(-90, -20, 150)" x="-20" y="150" font-family="Arial" font-size="12" text-anchor="middle">feature2</text>
    <text transform="rotate(-90, -20, 250)" x="-20" y="250" font-family="Arial" font-size="12" text-anchor="middle">feature3</text>
    <text transform="rotate(-90, -20, 350)" x="-20" y="350" font-family="Arial" font-size="12" text-anchor="middle">feature4</text>
    <!-- Color bar -->
    <rect x="430" y="50" width="20" height="300" fill="url(#gradient)"/>
    <text x="460" y="50" font-family="Arial" font-size="10" text-anchor="start">1.0</text>
    <text x="460" y="200" font-family="Arial" font-size="10" text-anchor="start">0.0</text>
    <text x="460" y="350" font-family="Arial" font-size="10" text-anchor="start">-1.0</text>
    <defs>
      <linearGradient id="gradient" x1="0" y1="0" x2="0" y2="1">
        <stop offset="0" stop-color="#3783b7"/>
        <stop offset="0.5" stop-color="#ffffff"/>
        <stop offset="1" stop-color="#ca4b56"/>
      </linearGradient>
    </defs>
  </g>
</svg>

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
