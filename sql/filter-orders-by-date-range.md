# Filter Orders by Date Range

> **Company:** Google | **Difficulty:** Easy

---

#### Objective
Construct a SQL query to fetch the `order_id`, `customer_name`, `order_date`, and `total_amount` from the `orders` table. The query should retrieve only those orders placed between January 1, 2023, and June 30, 2023, and the results must be ordered by the `order_date` in ascending order.

#### Additional information

The `orders` table:

| Column | Type | Description |
|--------|------|-------------|
| order_id | INTEGER | Unique identifier for each order |
| customer_name | VARCHAR | Name of the customer who placed the order |
| order_date | DATE | Date when the order was placed |
| total_amount | DECIMAL | Total monetary value of the order |

- Ensure that the `order_date` falls inclusively between '2023-01-01' and '2023-06-30'.
- The output should list the orders sorted from the earliest to the latest based on the `order_date`.
- Assume all dates are in the 'YYYY-MM-DD' format.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/filter-orders-by-date-range)
