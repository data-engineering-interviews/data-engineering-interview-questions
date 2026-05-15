# SQL JOIN with Pandas Data Processing and CSV Export

> **Company:** Intel | **Difficulty:** Medium

---

#### Scenario

A SQLite database contains sales data across multiple tables that need to be analyzed together.

#### Task

Write a Python script at `/home/interview/analyze_sales.py` that:
1. Connects to `/home/interview/sales.db`
2. Executes a SQL query using INNER JOIN to combine `customers`, `orders`, and `order_items` tables (customers → orders → order_items), filtering for orders with status `'completed'`
3. Loads the results into a pandas DataFrame
4. Calculates `total_amount` (quantity × unit_price) rounded to 2 decimal places for each order item
5. Calculates `customer_total` (sum of all total_amounts per customer) rounded to 2 decimal places and adds it as a column
6. Calculates `revenue_percentage` showing each customer's percentage of total revenue (customer_total / overall_total × 100), rounded to 2 decimal places
7. Exports the result to `/home/interview/sales_report.csv`



#### Database Schema

- `customers`: id, name, email, city, country
- `orders`: id, customer_id, order_date, status
- `order_items`: id, order_id, product_name, quantity, unit_price

---
