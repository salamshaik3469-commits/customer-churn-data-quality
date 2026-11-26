# Data Quality & Exploratory Analysis Report

## Objective
Prepare an analysis-ready customer churn dataset and document quality decisions and initial patterns.

## Dataset and limitation
The repository includes a 21-record synthetic sample with one deliberately duplicated record and several intentionally introduced data-quality issues. The Edvyro-provided CSV was not attached in the chat, so this is not claimed to be the portal's original dataset. Replace it with the supplied CSV if required.

## Quality checks
- Duplicate detection and removal.
- Numeric parsing for age, tenure and monthly charges.
- Missing-value and invalid-value checks.
- Plausibility ranges: age 18–100, tenure 0–120 months, monthly charges 0–1000.
- Standardization of known category variants.
- Validation of unique customer IDs and remaining missing values.

## Cleaning decisions
1. Remove exact duplicate rows.
2. Convert numeric columns safely; invalid text becomes missing.
3. Mark out-of-range numeric values as missing rather than guessing.
4. Standardize `month to month` to `Month-to-month` and `Fiber` to `Fiber optic`.
5. Fill numeric missing values with the column median.
6. Use `Unknown` for missing categorical values in tech support and payment method.
7. Validate the cleaned output and export it as CSV.

## Exploratory analysis
The notebook calculates descriptive statistics and churn rate, and plots churn counts, churn rate by contract type, and monthly charges by churn status. Interpret differences as associations, not proof of causation.

## Reproducibility
Run `notebooks/customer_churn_analysis.ipynb`. Required packages: pandas, numpy, matplotlib and Jupyter.

**Submission note:** This is a synthetic demonstration dataset. Do not describe its patterns as real company/customer findings.
