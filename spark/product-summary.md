# Product Summary

> **Company:** Amazon | **Difficulty:** Medium

---

#### Objective

You are working with a consumer goods company that tracks its product catalog, transaction-level sales, and warehouse inventory in three separate tables.

#### Task

Compute a summary for every product that includes total_quantity and total_revenue from the sales table, and total_stock from the inventory table summed across all warehouses. Aggregate the sales and inventory tables separately by product_id before combining them with the products table. Some products may have no sales records, and some may have no inventory records, so you need to choose a join type that preserves all products regardless. Any null values that appear in total_quantity, total_revenue, or total_stock after joining should be replaced with 0. The final output should contain product_id, name, category, total_quantity, total_revenue, and total_stock. Save your result as `result_df`.

#### File Path

- Products: `/home/interview/products.csv`
- Sales: `/home/interview/sales.csv`
- Inventory: `/home/interview/inventory.csv`
- Starter script: `/home/interview/product_summary.py`

#### Schema

**products.csv**

| Column     | Type    |
|------------|---------|
| product_id | integer |
| name       | string  |
| category   | string  |

**sales.csv**

| Column     | Type    |
|------------|---------|
| sale_id    | integer |
| product_id | integer |
| quantity   | integer |
| revenue    | float   |

**inventory.csv**

| Column     | Type    |
|------------|---------|
| product_id | integer |
| stock      | integer |
| warehouse  | string  |

**Expected output schema**

| Column         | Type    |
|----------------|---------|
| product_id     | integer |
| name           | string  |
| category       | string  |
| total_quantity | integer |
| total_revenue  | float   |
| total_stock    | integer |

#### **Example**

Given this sample input:

**products**

| product_id | name   | category   |
|------------|--------|------------|
| 1          | Cola   | Beverages  |
| 2          | Chips  | Snacks     |
| 3          | Apple  | Fruits     |

**sales**

| sale_id | product_id | quantity | revenue |
|---------|------------|----------|---------|
| 1       | 1          | 5        | 120.0   |
| 2       | 1          | 3        | 80.0    |
| 3       | 2          | 10       | 250.0   |

**inventory**

| product_id | stock | warehouse   |
|------------|-------|-------------|
| 1          | 50    | Warehouse_A |
| 1          | 30    | Warehouse_B |
| 3          | 100   | Warehouse_A |

The output would be:

| product_id | name  | category  | total_quantity | total_revenue | total_stock |
|------------|-------|-----------|----------------|---------------|-------------|
| 1          | Cola  | Beverages | 8              | 200.0         | 80          |
| 2          | Chips | Snacks    | 10             | 250.0         | 0           |
| 3          | Apple | Fruits    | 0              | 0.0           | 100         |

Cola has two sales totaling quantity 8 and revenue 200.0, and inventory across two warehouses totaling 80. Chips has sales but no inventory, so total_stock is 0. Apple has no sales but does have inventory, so total_quantity and total_revenue are 0.

---
