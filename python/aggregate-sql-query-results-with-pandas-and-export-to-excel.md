# Aggregate SQL Query Results with Pandas and Export to Excel

> **Company:** Meta | **Difficulty:** Medium

---

#### Scenario

A SQLite database contains customer and order data across multiple tables. You need to analyze total order values per customer and export the results to Excel.

#### Task

Write a Python script at `/home/interview/analyze_orders.py` that:
1. Connects to the SQLite database at `/home/interview/orders.db`
2. Executes a SQL query to fetch customer and order data (join the tables)
3. Loads the results into a pandas DataFrame
4. Calculates total order value per customer using pandas
5. Saves the results to `/home/interview/customer_totals.xlsx` with columns: `customer_id`, `customer_name`, `total_order_value`



#### Database Schema

**customers table:** id, first_name, last_name, email

**orders table:** id, customer_id, order_date, order_amount

---
