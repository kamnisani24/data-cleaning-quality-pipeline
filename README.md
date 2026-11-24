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

| Issue | Count |
|---|---:|
| Duplicate rows | 5,268 |
| Missing CustomerID | 135,037 |
| Missing Description | 1,454 |
| Invalid dates | 0 |
| Cancelled orders | 9,251 |
| Zero/negative price | 1,058 |
| Negative qty (not cancelled) | 474 |
| Quantity outliers flagged | 27,111 |
| Rows before cleaning | 541,909 |
| Rows after cleaning | 534,129 |

## Key Findings & Insights

- Analyzed 541,909 raw transaction records from the Online Retail dataset.
- Identified 5,268 duplicate rows.
- Missing CustomerID was the largest data quality issue, affecting 135,037 records.
- Found 1,454 records with missing product descriptions.
- Identified 9,251 cancelled orders.
- Detected 1,058 records with zero or negative prices.
- Found 474 records with negative quantities in non-cancelled orders.
- Flagged 27,111 quantity outliers using the IQR method without automatically deleting them.
- No invalid dates were found.
- The final dataset contained 534,129 records after cleaning.

## Key Learnings

- Missing values can significantly affect data quality and analysis.
- Outliers should be investigated before removal because some may represent genuine wholesale orders.
- Cancelled transactions should be handled separately from regular sales analysis.
- Data validation and cleaning improve the reliability of further analysis.

## Limitations

- Outliers were flagged for review rather than automatically removed.
- The project focuses on data cleaning and quality validation, not predictive modelling.
