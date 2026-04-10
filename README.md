# Supermarket Sales Analysis

## Overview

This project explores supermarket transaction data to understand profitability patterns and evaluate whether customer satisfaction (`Rating`) is related to gross income.

The analysis combines data cleaning, exploratory analysis, correlation analysis, and visual reporting to produce a concise set of business-facing findings.

## Objective

The goal of this project is to:

- inspect and prepare supermarket transaction data for analysis
- explore profitability patterns across branches, customers, and payment methods
- assess whether customer rating is related to gross income
- visualize key distributions and relationships
- summarize findings in a recruiter-friendly report

## Dataset

**Source:** Kaggle — Supermarket Sales  
https://www.kaggle.com/aungpyaeap/supermarket-sales

Dataset scope:

- time period: January to March 2019
- branches: A, B, and C
- multiple cities, product lines, and payment methods

The dataset includes financial metrics, transaction-level variables, and customer ratings.

## Tools

- Python
- pandas
- NumPy
- matplotlib
- seaborn
- scipy

Optional:

- ydata-profiling
- calmap

## What This Project Does

The notebook covers a structured EDA workflow:

- loads and inspects transaction data
- checks data types, missing values, and duplicates
- performs simple imputation for missing values
- explores distributions of numeric variables
- compares gross income across branch, gender, and payment method
- analyzes the relationship between rating and gross income
- aggregates average gross income over time
- examines pairwise numeric relationships
- computes and visualizes a correlation matrix
- saves key charts for use in the portfolio

## Highlights

High-level results from the analysis include:

- ratings are broadly uniform and show no strong skew
- rating and gross income have almost no linear relationship (correlation ≈ -0.04)
- branch-level gross income distributions overlap heavily, though Branch C appears slightly higher in median gross income
- gender and payment method show minimal differences in gross income distribution
- financial variables such as `Tax 5%`, `Total`, `cogs`, and `gross income` are highly correlated because they are derived from shared calculations
- average gross income fluctuates over time with no clear sustained trend across the three-month period

## Outputs

This project includes:

- `supermarket_sales_analysis.ipynb` — main analysis notebook
- `report.md` — written summary of findings
- saved figures in the `figures/` folder, including:
  - `avg_gross_income_over_time.png`
  - `correlation_heatmap.png`
  - `gross_income_by_branch.png`
  - `gross_income_by_gender.png`
  - `rating_distribution.png`
  - `rating_vs_gross_income_regression.png`

## Project Structure

```text
python-supermarket-sales-analysis/
├── data/
│   ├── README.md
│   └── supermarket_sales.csv
├── figures/
│   ├── .gitkeep
│   ├── avg_gross_income_over_time.png
│   ├── correlation_heatmap.png
│   ├── gross_income_by_branch.png
│   ├── gross_income_by_gender.png
│   ├── rating_distribution.png
│   └── rating_vs_gross_income_regression.png
├── notebooks/
│   └── supermarket_sales_analysis.ipynb
├── README.md
├── report.md
└── requirements.txt
```

## How to Run

1. Open the notebook in Jupyter Notebook, JupyterLab, or VS Code.
2. Make sure the dataset is available in the `data/` folder.
3. Install the required dependencies.
4. Run all notebook cells from top to bottom.
5. Review the saved figures and written report for the final outputs.

Example dependency install:

```bash
pip install pandas numpy matplotlib seaborn scipy
```

## Notes

- Missing values are handled with simple baseline imputation:
  - numeric columns → mean
  - categorical columns → mode
- Duplicate rows are removed before analysis.
- Some financial columns are derived from one another, so high correlations among them are expected.
- This project is focused on exploratory analysis and interpretation rather than predictive modeling.

## Future Improvements

Potential next steps include:

- segmenting profitability by product line, customer type, city, and branch
- adding time features such as day of week or hour of day
- testing more robust imputation approaches
- building a lightweight predictive model using independent variables only
- expanding the report with more business recommendations