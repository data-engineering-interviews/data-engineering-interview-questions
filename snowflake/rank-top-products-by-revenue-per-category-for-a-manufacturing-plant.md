# Rank Top Products by Revenue per Category

> **Company:** Coinbase | **Difficulty:** Hard

---

#### Scenario

You work at a manufacturing company and have access to product information and sales records.

#### Task

Write a Snowflake SQL query that:
1. Joins `{{ ref("products") }}` with `{{ ref("sales") }}` on `product_id`
2. Calculates the total revenue per product
3. Ranks products within each category by total revenue in descending order using `DENSE_RANK` (rank 1 is the highest revenue)
4. Returns only the top 3 ranked products per category
5. Returns the columns: `category`, `product_name`, `total_revenue`, `rank`

#### Schema

**products**

| Column | Type | Description |
|--------|------|-------------|
| product_id | Integer | Unique product identifier |
| category | String | Product category |
| product_name | String | Name of the product |

**sales**

| Column | Type | Description |
|--------|------|-------------|
| sale_id | Integer | Unique sale identifier |
| product_id | Integer | Foreign key to products |
| quantity | Integer | Number of units sold |
| revenue | Double | Revenue from the sale |

#### Example

**products:**

| product_id | category | product_name |
|---|---|---|
| 1 | Electronics | Laptop |
| 2 | Electronics | Tablet |
| 3 | Electronics | Headphones |
| 4 | Clothing | Jacket |
| 5 | Clothing | Sneakers |
| 6 | Clothing | T-Shirt |

**sales:**

| sale_id | product_id | quantity | revenue |
|---|---|---|---|
| 1 | 1 | 3 | 500.00 |
| 2 | 1 | 2 | 300.00 |
| 3 | 2 | 4 | 250.00 |
| 4 | 2 | 3 | 200.00 |
| 5 | 3 | 5 | 75.00 |
| 6 | 3 | 4 | 50.00 |
| 7 | 4 | 2 | 350.00 |
| 8 | 5 | 3 | 220.00 |
| 9 | 6 | 6 | 80.00 |

**Expected Output:**

| category | product_name | total_revenue | rank |
|---|---|---|---|
| Clothing | Jacket | 350.00 | 1 |
| Clothing | Sneakers | 220.00 | 2 |
| Clothing | T-Shirt | 80.00 | 3 |
| Electronics | Laptop | 800.00 | 1 |
| Electronics | Tablet | 450.00 | 2 |
| Electronics | Headphones | 125.00 | 3 |

> **Note:** Each product's revenue is summed across all its sales records before ranking. Since each category has exactly 3 products, all products appear in the output.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/rank-top-products-by-revenue-per-category-for-a-manufacturing-plant)
