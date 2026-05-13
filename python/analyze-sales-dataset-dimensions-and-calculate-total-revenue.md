# Analyze Sales Dataset Dimensions and Calculate Total Revenue

> **Company:** Databricks | **Difficulty:** Easy

---

#### Scenario

A sales dataset needs to be analyzed to determine its size characteristics and calculate key metrics. You need to load the data, report its dimensions, classify its size, and calculate total revenue.

#### Task

Write a Python script at `/home/interview/analyze_sales.py` that loads the sales dataset from `/home/interview/sales_data.csv`, calculates dimensions (rows and columns), determines the total number of cells, classifies the dataset size based on cell count, and calculates the total sales revenue. Save the results to `/home/interview/sales_report.json`.

#### Size Classification

- **Small**: < 10,000 cells
- **Medium**: 10,000 - 99,999 cells
- **Large**: >= 100,000 cells

#### Example

Expected output format in `/home/interview/sales_report.json`:
```json
{
  "rows": 250,
  "columns": 8,
  "total_cells": 2000,
  "size_classification": "small",
  "total_revenue": 125430.50
}
```

