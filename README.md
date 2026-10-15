# Task 1 — Exploratory Data Analysis

## Project summary
A complete, reproducible EDA of the public diabetes progression dataset: profiling, data quality checks, documented cleaning choices, statistical visualizations, and evidence-based findings.

## Dataset
- Source: `sklearn.datasets.load_diabetes` (public dataset bundled with scikit-learn).
- Included local copy: `diabetes_eda_dataset.csv`
- Size: 442 rows × 11 columns (10 predictors and 1 target).
- Target: quantitative one-year disease progression measure.
- Important: predictor columns are pre-scaled/standardized by the dataset provider; they are not raw clinical units.

## Deliverables
- `Task1_Exploratory_Data_Analysis.ipynb` — notebook with markdown commentary, code, and executed outputs.
- `diabetes_eda_dataset.csv` — local dataset used by the notebook.
- `visualizations/` — high-resolution PNG exports of the key charts.
- `EDA_Findings_Report.md` — concise written report with calculated results.

## Key analytical decisions
1. **Missing data:** count missing cells; median-impute numeric columns only if missing values are present. Median is robust to extreme values.
2. **Duplicates:** report exact duplicate rows; remove only if present.
3. **Outliers:** flag values beyond Q1 − 1.5×IQR or Q3 + 1.5×IQR. Keep flagged observations unless independent evidence establishes an error.
4. **Correlation:** use Pearson r for linear associations; do not infer causation.
5. **Reproducibility:** data is local; notebook does not need to fetch it from the internet.

## How to run
Recommended: Python 3.10+.

```bash
python -m venv .venv
# Windows:
.venv\\Scripts\\activate
# macOS/Linux:
source .venv/bin/activate

pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook Task1_Exploratory_Data_Analysis.ipynb
```

Open the notebook from this project folder and choose **Run All**. The CSV and `visualizations/` directory should remain beside the notebook.

## Main packages
Python, pandas, NumPy, Matplotlib, Seaborn, scikit-learn, Jupyter Notebook.

## Responsible interpretation
This is descriptive analysis of a small study dataset, not a diagnostic tool. Predictor values are standardized and relationships are observational. No clinical or causal conclusions should be drawn.
