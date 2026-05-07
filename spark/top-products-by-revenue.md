# Top Products by Revenue

> **Company:** Walmart | **Difficulty:** Medium

---

#### Objective

You are analyzing sales data for a large retail company that tracks products and individual sale transactions in separate tables.

#### Task

Find the top 3 selling products in each category based on total revenue. A product may appear in multiple rows of the sales table, so you need to first aggregate revenue by product. Join the aggregated sales data with the products table to get each product's category and name. Then use a window function with `dense_rank` to rank products within each category by total revenue in descending order. Dense ranking means there are no gaps in the rank sequence when products are tied. Keep only products with a rank of 3 or less. Save your result as `result_df`.

#### File Path

- Products: `/home/interview/products.csv`
- Sales: `/home/interview/sales.csv`
- Starter script: `/home/interview/top_products.py`

#### Schema

**products.csv**

| Column       | Type    |
|--------------|---------|
| product_id   | integer |
| category     | string  |
| product_name | string  |

**sales.csv**

| Column     | Type    |
|------------|---------|
| sale_id    | integer |
| product_id | integer |
| quantity   | integer |
| revenue    | float   |

**Expected output schema**

| Column       | Type    |
|--------------|---------|
| category     | string  |
| product_name | string  |
| revenue      | float   |
| rank         | integer |

#### **Example**

Given this sample input:

**products**

| product_id | category    | product_name |
|------------|-------------|--------------|
| 1          | Electronics | Laptop       |
| 2          | Electronics | Tablet       |
| 3          | Electronics | Headphones   |
| 4          | Clothing    | Jacket       |
| 5          | Clothing    | Sneakers     |
| 6          | Clothing    | T-Shirt      |

**sales**

| sale_id | product_id | quantity | revenue |
|---------|------------|----------|---------|
| 1       | 1          | 2        | 100.0   |
| 2       | 1          | 1        | 80.0    |
| 3       | 2          | 3        | 120.0   |
| 4       | 3          | 1        | 50.0    |
| 5       | 4          | 2        | 70.0    |
| 6       | 5          | 1        | 50.0    |
| 7       | 6          | 4        | 30.0    |

The output would be:

| category    | product_name | revenue | rank |
|-------------|--------------|---------|------|
| Electronics | Laptop       | 180.0   | 1    |
| Electronics | Tablet       | 120.0   | 2    |
| Electronics | Headphones   | 50.0    | 3    |
| Clothing    | Jacket       | 70.0    | 1    |
| Clothing    | Sneakers     | 50.0    | 2    |
| Clothing    | T-Shirt      | 30.0    | 3    |

Laptop has two sales totaling $180.0 (100.0 + 80.0), making it the top product in Electronics. Each category's products are ranked independently by their aggregated revenue.

---
