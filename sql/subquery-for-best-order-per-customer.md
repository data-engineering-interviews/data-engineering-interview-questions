# Subquery for Best Order per Customer

> **Company:** Anthropic | **Difficulty:** Medium

---

#### Objective
Given two tables, `customers` and `orders`, write an SQL query to retrieve each customer's name along with the ID and total amount of their highest-value order. The results should be ordered alphabetically by the customer's name.

#### Additional information
- Each customer may have multiple orders.
- If a customer has multiple orders with the same highest total amount, return the order with the smallest `order_id`.

The `customers` table:

| Column | Type | Description |
|--------|------|-------------|
| customer_id | integer | Unique identifier for each customer |
| customer_name | string | Name of the customer |

The `orders` table:

| Column | Type | Description |
|--------|------|-------------|
| order_id | integer | Unique identifier for each order |
| customer_id | integer | Identifier linking the order to a customer |
| total_amount | decimal | Total amount of the order |

- Ensure that all customers with at least one order are included in the result.
- Order the final output by `customer_name` in ascending order.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/subquery-for-best-order-per-customer)
