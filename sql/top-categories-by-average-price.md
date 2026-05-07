# Top Categories by Average Price

> **Company:** Samsung | **Difficulty:** Hard

---

#### Objective
Write an SQL query to find the top 3 product categories with the highest average price. For each of these categories, return the number of active products, the average price rounded to two decimal places, and the count of products with low stock (less than 10 units).

#### Additional information
- Only consider active products (`is_active = true`).
- If multiple categories have the same average price, order them by the number of active products in descending order.
- Return the results ordered by average price in descending order first, then by product count in descending order.
- The results should be limited to the top 3 categories.
- The `products` table contains information about the products.
- The `inventory` table contains information about the stock levels of the products.

Constraints:
- You can assume that `products` and `inventory` tables are non-empty.
- Each product in the `products` table has a corresponding entry in the `inventory` table.

Clarifications:
- `avg_price` should be the average price of the active products in each category.
- `product_count` should be the count of active products in each category.
- `low_stock_items` should be the count of active products with a stock level less than 10 in each category.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/top-categories-by-average-price)
