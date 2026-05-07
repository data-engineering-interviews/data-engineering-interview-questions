# Find Customers Without Orders

> **Company:** LinkedIn | **Difficulty:** Easy

---

#### Objective
Construct an SQL query to identify and list the names of all customers who have never placed an order. Ensure the resulting list is ordered alphabetically by the customers' names.

#### Additional information
You are provided with two tables:

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
| order_date | date | The date on which the order was placed |

Your query should return a table with a single column, `customer_name`, containing the names of customers who have no corresponding entries in the `orders` table. If every customer has placed at least one order, the query should return an empty result set.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/find-customers-without-orders)
