# Convert Excel Files with Multiple Sheets to Individual CSV Files

> **Company:** Airbnb | **Difficulty:** Easy

---

#### Scenario

A directory contains multiple Excel files with multiple sheets that need to be converted to individual CSV files for processing.

#### Task

Write a Python script at `/home/interview/convert_excel.py` that reads all Excel files from `/home/interview/excel_files/`, converts each sheet to a separate CSV file, and saves them to `/home/interview/csv_output/` with the naming convention `filename_sheetname.csv`.

#### Example

Input:
```
excel_files/
  ├── sales_data.xlsx (3 sheets: Q1_Sales, Q2_Sales, Q3_Sales)
  └── inventory.xlsx (2 sheets: Electronics, Furniture)
```

Expected output:
```
csv_output/
  ├── sales_data_Q1_Sales.csv
  ├── sales_data_Q2_Sales.csv
  ├── sales_data_Q3_Sales.csv
  ├── inventory_Electronics.csv
  └── inventory_Furniture.csv
```

---
