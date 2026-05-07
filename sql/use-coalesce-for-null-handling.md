# Use COALESCE for Null Handling

> **Company:** Samsung | **Difficulty:** Easy

---

#### Objective
Given a table named `orders` with the columns `order_id`, `customer_name`, `discount`, and `total_amount`, write an SQL query to retrieve all orders. Replace any `NULL` values in the `discount` column with `0`. The result should be ordered by `order_id` in ascending order.

#### Additional information
- The `orders` table schema:

| Column | Type | Description |
|--------|------|-------------|
| order_id | Integer | Unique identifier for each order |
| customer_name | String | Name of the customer who placed the order |
| discount | Decimal | Discount amount applied to the order, can be `NULL` |
| total_amount | Decimal | Total amount of the order |

- Ensure that the `discount` column in the result does not contain any `NULL` values; use `0` instead where applicable.
- The output should include all columns: `order_id`, `customer_name`, `discount`, and `total_amount`, in that order.
- Order the results by `order_id` in ascending order.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/use-coalesce-for-null-handling)
