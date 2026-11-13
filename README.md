# Data Cleaning & Quality Validation Pipeline

Python/Pandas workflow to clean a raw retail transactions dataset and generate a data quality report.

## Dataset
Online Retail Dataset (UK-based online store transactions) from Kaggle.

## What this project does
- Removes duplicate rows
- Handles missing values (CustomerID, Description)
- Converts and validates the date format
- Flags cancelled orders (invoice numbers starting with "C")
- Removes invalid records (zero/negative price, negative quantity in non-cancelled orders)
- Standardizes text in product descriptions
- Flags quantity outliers using the IQR method (flagged, not deleted)
- Generates a data quality report and a chart of issues found

## Files
- `notebook22a202e458.ipynb`: full code and outputs
- `data_quality_report.csv`: count of each issue found, plus rows before and after cleaning
- `quality_issues_chart.png`: chart of data quality issues

## Tools
Python, Pandas, Matplotlib

## Key learnings
- Missing CustomerID was the biggest data quality issue in this dataset
- Outliers were flagged instead of deleted, since large orders can be genuine wholesale purchases
- Cancelled orders were kept separate, as they affect sales analysis
