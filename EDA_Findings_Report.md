# EDA Findings Report — Task 1

## Executive summary
This project explores a public diabetes progression dataset containing **442 rows** and **10 predictors plus one target**. The analysis checks data quality, summarizes distributions, screens possible outliers using the 1.5×IQR rule, and examines linear associations.

## Data quality and cleaning
- **Missing cells:** 0
- **Exact duplicate rows:** 0
- **Cleaning outcome:** No imputation was needed. No duplicate removal was needed.
- **Outlier method:** IQR fences, where IQR = Q3 − Q1 and fences are Q1 − 1.5×IQR / Q3 + 1.5×IQR.
- **Outlier policy:** flagged values were retained because an IQR flag is not proof of invalid data. Predictors are already standardized, and unusual values can represent valid variation.

## Target distribution
- Mean: **152.13**
- Median: **140.50**
- Standard deviation: **77.09**

## Strongest correlations with target
- **bmi**: Pearson r = 0.586
- **s5**: Pearson r = 0.566
- **bp**: Pearson r = 0.441
- **s4**: Pearson r = 0.430

These are linear associations, not causal effects. Scatterplots should be reviewed for curvature, clusters, and unusual observations before any modeling decisions.

## Weakest correlations with target
- **s2**: Pearson r = 0.174
- **sex**: Pearson r = 0.043

## Actionable implications
1. Use the strongest observed associations as candidates for deeper domain-informed analysis, not as proof of cause.
2. Investigate scatterplots and potential nonlinear patterns before selecting a model.
3. Keep a data-cleaning audit trail. Do not delete outliers just to improve visual appearance or correlation strength.
4. For a later predictive task, create train/test splits first and fit imputation/scaling steps only on training data to avoid leakage.

## Limitations
- The dataset is small (442 rows) and reflects a particular study population.
- Predictors are standardized and should not be interpreted as raw clinical units.
- Correlation does not establish causation; no individual-level diagnosis or treatment inference is appropriate.
