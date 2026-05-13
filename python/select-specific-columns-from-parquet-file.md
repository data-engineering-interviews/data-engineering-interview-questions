# Select Specific Columns from Parquet File

> **Company:** OpenAI | **Difficulty:** Easy

---

#### Scenario

A Parquet file contains customer data with many columns, but only a subset of columns is needed for analysis.

#### Task

Write a Python script at `/home/interview/select_columns.py` using pandas that reads `/home/interview/customers.parquet`, selects only the columns `id`, `first_name`, `last_name`, `email`, and `total_purchases`, and writes the result to `/home/interview/selected_data.parquet`.

