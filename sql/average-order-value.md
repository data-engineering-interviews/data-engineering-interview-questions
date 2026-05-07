# Average Order Value

> **Company:** Accenture | **Difficulty:** Easy

---

#### Objective
Given a table named `Orders` that records customer purchases, write an SQL query to determine the average expenditure per customer. Your result should display each `customer_id` alongside their `avg_order_value`, rounded to two decimal places. Ensure the output is sorted in ascending order based on `customer_id`.

#### Additional information
- **Table Schema:**

  The `orders` table:

  | Column | Type | Description |
  |--------|------|-------------|
  | order_id | INTEGER | Unique identifier for each order |
  | customer_id | INTEGER | Identifier for the customer who made the order |
  | total_amount | DECIMAL | Total amount spent on the order |
  | order_date | DATE | Date when the order was placed |

- **Constraints:**
  - Each `customer_id` may have multiple associated orders.
  - There is at least one order present in the table.
- **Output Requirements:**
  - Columns: `customer_id`, `avg_order_value`
  - `avg_order_value` must be rounded to two decimal places.
  - Results must be ordered by `customer_id` in ascending order.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/average-order-value)
