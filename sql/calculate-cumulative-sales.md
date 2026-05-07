# Calculate Cumulative Sales

> **Company:** Uber | **Difficulty:** Medium

---

#### Objective
Given a table `sales_data` containing product sales with the following columns:

| Column | Type | Description |
|--------|------|-------------|
| daily_sales | INTEGER | The number of units sold on that date |
| date | DATE | The date of the sale |
| product_name | VARCHAR | The name of the product sold |

Write a SQL query to retrieve each record along with a new column `cumulative_sales` that represents the running total of sales for each product up to and including the current date. The results should be ordered first by `product_name` and then by `date`.

#### Additional information
- **Constraints:**
  - The `sales_data` table can contain multiple products with sales data spanning multiple dates.
  - Dates for each product are unique and sorted chronologically.
  
- **Output Format:**
  - The output should include the following columns: `cumulative_sales`, `daily_sales`, `date`, `product_name`.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/calculate-cumulative-sales)
