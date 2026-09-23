# Stroke Data Analysis

**COMP3125 – Group Project**  
Department of Data Science

An exploratory data analysis project examining how residence type, work type, and smoking status relate to recorded stroke status. The notebook uses Python, pandas, SciPy, Matplotlib, and statsmodels on the 5,110-row [Stroke Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset).

## Questions

1. Is there a relationship between residence type (urban versus rural) and stroke risk?
2. Does work type affect stroke risk directly, or is the relationship explained by age, blood pressure, glucose level, or BMI?
3. Is there a relationship between smoking status and stroke risk?

## Analysis

- Checked missing values and duplicates. BMI is missing in 201 records; the analysis drops those rows and uses 4,909 complete cases.
- Compared stroke counts and observed rates across residence, work, and smoking categories using tables, plots, and chi-square tests.
- Fit an exploratory logistic regression with work type, age, BMI, average glucose, and hypertension.

## Findings

| Comparison | Notebook result | Interpretation |
| --- | --- | --- |
| Urban versus rural residence | Chi-square p = 0.725 | No clear association in this sample. |
| Work type | Chi-square p = 1.71 × 10⁻⁸ | An unadjusted association. Work categories differ in age, so this does not establish a direct work-type effect. |
| Smoking status (excluding `Unknown`) | Chi-square p = 0.04996 | Borderline, unadjusted evidence; interpret cautiously. |

**Regression caveat:** The logistic regression in the notebook issued a convergence warning. Its work-type coefficient p-values should not be used to conclude that the association disappears after adjustment. The model needs a revised specification and convergence checks before that claim can be made.

This is an observational classroom analysis, not a clinical risk model or a causal study. The small number of stroke cases, complete-case filtering, and multiple exploratory tests limit the conclusions.

## Run in Google Colab

1. Open [the notebook](Stroke_data_analysis_(5).ipynb) and click its **Open in Colab** badge.
2. Run the notebook's cells in order. The first data-loading cell installs `kagglehub`, downloads the [Stroke Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset) from Kaggle, and reads the CSV automatically.

The CSV is downloaded at runtime and is not stored in this repository. If Kaggle requires consent for access, follow its prompt. The displayed analysis outputs are from the author's earlier run; rerun the notebook to reproduce them.
