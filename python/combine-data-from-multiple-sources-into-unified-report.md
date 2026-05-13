# Combine Data from Multiple Sources into Unified Report

> **Company:** Vercel | **Difficulty:** Hard

---

#### Scenario

Order data is distributed across three different sources: an API provides order information, a CSV file contains customer details, and a SQLite database stores product information. You need to combine all three sources into a unified report.

#### Task

Write a Python script at `/home/interview/generate_report.py` that:
1. Fetches order data from the API at `http://api.orders.local/orders`
2. Reads customer data from `/home/interview/customers.csv`
3. Queries product data from the SQLite database at `/home/interview/orders.db` (table: `products`)
4. Combines all three sources and writes a unified report to `/home/interview/order_report.csv`

The report should include: `order_id`, `customer_name`, `email`, `country`, `order_date`, `status`, `product_name`, `quantity`, `price`, `total_amount`

Calculate `total_amount` as `quantity × price` and round to 2 decimal places.

