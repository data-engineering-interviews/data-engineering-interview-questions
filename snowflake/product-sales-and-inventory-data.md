# Product Sales and Inventory Data

> **Company:** PayPal | **Difficulty:** Medium

---

#### Scenario

You work for a food and beverage company and have three tables containing product details, sales records, and inventory stock levels across warehouses.

#### Task

Write a Snowflake SQL query that:
1. Aggregates `{{ ref("sales") }}` to compute `total_quantity` (sum of `quantity`) and `total_revenue` (sum of `revenue`) per product
2. Aggregates `{{ ref("inventory") }}` to compute `total_stock` (sum of `stock`) per product
3. Joins both aggregations to `{{ ref("products") }}` using `LEFT JOIN` so all products appear even if they have no sales or inventory records
4. Replaces any `NULL` values in `total_quantity`, `total_revenue`, and `total_stock` with `0`
5. Returns columns: `product_id`, `name`, `category`, `total_quantity`, `total_revenue`, `total_stock`

#### Schema

**products**

| Column | Type | Description |
|--------|------|-------------|
| product_id | Integer | Unique product identifier |
| name | String | Product name |
| category | String | Product category |

**sales**

| Column | Type | Description |
|--------|------|-------------|
| sale_id | Integer | Unique sale identifier |
| product_id | Integer | Product that was sold |
| quantity | Integer | Number of units sold |
| revenue | Integer | Revenue from the sale |

**inventory**

| Column | Type | Description |
|--------|------|-------------|
| product_id | Integer | Product identifier |
| stock | Integer | Units in stock |
| warehouse | String | Warehouse location |

#### Example

**products:**

| product_id | name | category |
|---|---|---|
| 1 | Green Tea | Beverages |
| 2 | Trail Mix | Snacks |
| 3 | Sparkling Water | Beverages |
| 4 | Granola Bar | Snacks |
| 5 | Mango Smoothie | Beverages |

**sales:**

| sale_id | product_id | quantity | revenue |
|---|---|---|---|
| 1 | 1 | 12 | 24 |
| 2 | 1 | 8 | 16 |
| 3 | 2 | 5 | 15 |
| 4 | 3 | 20 | 40 |
| 5 | 4 | 3 | 9 |

**inventory:**

| product_id | stock | warehouse |
|---|---|---|
| 1 | 60 | WarehouseA |
| 2 | 45 | WarehouseA |
| 3 | 30 | WarehouseB |
| 4 | 25 | WarehouseA |
| 5 | 15 | WarehouseB |

**Expected Output:**

| product_id | name | category | total_quantity | total_revenue | total_stock |
|---|---|---|---|---|---|
| 1 | Green Tea | Beverages | 20 | 40 | 60 |
| 2 | Trail Mix | Snacks | 5 | 15 | 45 |
| 3 | Sparkling Water | Beverages | 20 | 40 | 30 |
| 4 | Granola Bar | Snacks | 3 | 9 | 25 |
| 5 | Mango Smoothie | Beverages | 0 | 0 | 15 |

> **Note:** Product 5 (Mango Smoothie) has no sales records, so `total_quantity` and `total_revenue` are `0` instead of `NULL`. All products appear in the output regardless of whether they have sales or inventory records.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/product-sales-and-inventory-data)
