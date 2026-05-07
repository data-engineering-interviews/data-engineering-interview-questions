# Customer Order Aggregation

> **Company:** BMW | **Difficulty:** Medium

---

#### Objective

Write a SQL query that retrieves the names and email addresses of customers who have placed more than two orders. Additionally, for each customer, calculate the total number of orders they have placed and the total amount they have spent. The result should be sorted in descending order based on the total amount spent.

#### Additional Information

- The database consists of two tables: `customers` and `orders`.
- If a customer has not placed any orders, the total amount spent should be considered as 0.
- The output should include the following columns: `customer_name`, `email`, `total_orders`, and `total_spent`.
- The results should be sorted in descending order by `total_spent`.

<br />

The `customers` table:

| Column | Type |
|--------|------|
| id | integer |
| customer_name | string |
| email | string |

The `orders` table:

| Column | Type |
|--------|------|
| id | integer |
| customer_id | integer |
| amount | decimal |

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/customer-order-aggregation)
