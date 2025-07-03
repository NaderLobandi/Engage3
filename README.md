# Engage3 Assignment

This repository contains my completed solution to the Engage3 interview assignment. The task involved analyzing retail pricing data using Python and Jupyter Notebook. The project is divided into two main parts:

---

## Question 1: Cross-tabulation of Regional Prices

The first task was to aggregate pricing data across multiple files and produce a table that compares product prices (`UPC`) across different regions, broken down by retailer (`Banner`). I performed the following steps:

- Merged `prices.csv` with `stores.json` to attach region and banner information to each store.
- Computed the **median price** for each `UPC` at each `Banner` and `Region` combination.
- Pivoted the result to a wide format showing each region as a column.
- Exported the final table as a CSV file, structured similarly to the provided example.

---

## Question 2: Data Quality and Anomaly Investigation

I performed a thorough data validation and anomaly analysis in four parts:

### 1. Outlier Detection

- Grouped prices by `UPC`, `Banner`, and `Region`.
- Calculated standard deviation and price ranges.
- No extreme outliers were found using thresholds of standard deviation > 1 or price range > $2.

### 2. Regional Price Inconsistencies

- Compared expected pricing relationships between regions (e.g., Northern California > Kansas).
- Found **20 products** where **Kansas or Texas had higher prices** than expected. Most of these involved **Whole Foods** and **Walmart**, which may indicate pricing anomalies or data entry issues.

### 3. Missing or Invalid Data

- Identified **804 rows** with missing region and banner metadata due to unmatched `Store ID`s not present in `stores.json`.
- All prices in these rows were positive and plausible.
- These records were excluded from regional analyses due to missing geographic context.

### 4. Auditor Behavior Analysis

- Merged with `auditors.csv` and calculated per-auditor price statistics.
- Flagged **8 auditors** with very high price variability (standard deviation > 10 or price range > $50).
- These auditors may have been assigned diverse store types or may need review for consistency.

---

## Project Structure

Engage3/
├── Engage3.ipynb # main Jupyter notebook with analysis and commentary
├── prices.csv # product pricing data
├── stores.json # store metadata including region and banner
├── auditors.csv # auditor assignment metadata
├── README.md # this file

---

## Notes

- All code is written in Python and runs without errors in a clean environment.
- All assumptions, reasoning, and findings are documented using Markdown cells within the notebook.
- Data validation and anomaly detection were guided by both statistical intuition and domain context.
