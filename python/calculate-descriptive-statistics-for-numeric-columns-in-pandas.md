# Calculate Descriptive Statistics for Numeric Columns in Pandas

> **Company:** Google | **Difficulty:** Easy

---

#### Scenario

A CSV file contains e-commerce transaction data with both numeric and non-numeric columns. You need to generate a statistical summary report for all numeric columns.

#### Task

Write a Python script at `/home/interview/calculate_stats.py` using pandas that reads `/home/interview/sales_data.csv`, calculates descriptive statistics (mean, median, std, min, max, and quartiles: 25%, 50%, 75%) for all numeric columns only, and saves the results to `/home/interview/statistics_report.csv`. Round all values to 2 decimal places.

#### Example

Expected output format in `statistics_report.csv`:
```
statistic,price,quantity,discount_percent,shipping_cost,tax_amount
mean,45.23,3.42,12.45,8.90,4.12
median,42.00,3.00,10.00,7.50,3.80
std,15.67,2.31,8.45,3.20,2.10
min,10.00,1.00,0.00,2.50,0.50
25%,32.50,2.00,5.00,6.00,2.50
50%,42.00,3.00,10.00,7.50,3.80
75%,55.00,5.00,18.00,11.00,5.50
max,99.99,10.00,50.00,20.00,15.00
```