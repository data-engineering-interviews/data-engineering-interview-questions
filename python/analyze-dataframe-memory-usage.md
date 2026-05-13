# Analyze DataFrame Memory Usage

> **Company:** SAP | **Difficulty:** Easy

---

#### Scenario

A large dataset needs memory analysis to understand which columns consume the most memory and identify optimization opportunities.

#### Task

Write a Python script at `/home/interview/analyze_memory.py` using pandas that reads `/home/interview/sales_data.csv`, calculates the memory usage of each column in megabytes (rounded to 2 decimal places), and saves the report to `/home/interview/memory_report.csv`.

*Note: pandas is already installed.*

#### Example

Expected output format in `/home/interview/memory_report.csv`:
```
column_name,memory_mb
product_name,2.15
customer_email,1.83
quantity,0.08
order_date,0.08
```