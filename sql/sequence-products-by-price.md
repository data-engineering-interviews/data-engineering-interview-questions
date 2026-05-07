# Sequence Products by Price

> **Company:** GoDaddy | **Difficulty:** Hard

---

#### Objective
Given a table named `products`, you need to compute a new column named `neighbor_product`. This column should contain the product of the prices of the immediate previous and next products based on the ascending order of prices. If there is no previous or next product, treat the missing price as 0.

Write a SQL query to achieve this. Your query should return the product name, price, and the calculated `neighbor_product` for each product, ordered by price in ascending order.

#### Additional information

The `products` table:

| Column | Type | Description |
|--------|------|-------------|
| id | integer | A unique identifier for each product |
| product_name | string | The name of the product |
| price | integer | The price of the product |

- Constraints:
  - Each product will have a unique price.
  - There will be at least one product in the table.
- Special remarks:
  - Use SQL window functions to access the previous and next prices in the sorted list.
  - Consider using `COALESCE` to handle cases where the previous or next price is missing.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/sequence-products-by-price)
