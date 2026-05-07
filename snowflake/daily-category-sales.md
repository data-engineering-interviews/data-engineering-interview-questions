# Daily Category Sales

> **Company:** Snowflake | **Difficulty:** Easy

---

#### Scenario

You work at an online bookstore and have been given two tables containing daily sales transactions and product details.

#### Task

Write a Snowflake SQL query that:
1. Joins `{{ ref("sales") }}` with `{{ ref("products") }}` on `product_id`
2. Groups by `sale_date` and `category`
3. Calculates `total_quantity` as the sum of `quantity_sold`
4. Orders the result by `sale_date` ascending, then `category` ascending

#### Schema

**sales**

| Column | Type | Description |
|--------|------|-------------|
| sale_id | String | Unique identifier for the sale |
| product_id | String | Identifier for the product sold |
| sale_date | Date | Date of the sale |
| quantity_sold | Integer | Number of units sold in this transaction |

**products**

| Column | Type | Description |
|--------|------|-------------|
| product_id | String | Unique identifier for the product |
| product_name | String | Name of the product |
| category | String | Category the product belongs to |

#### Example

**sales:**

| sale_id | product_id | sale_date | quantity_sold |
|---|---|---|---|
| T1 | B1 | 2024-03-01 | 5 |
| T2 | B2 | 2024-03-01 | 8 |
| T3 | B3 | 2024-03-02 | 3 |
| T4 | B4 | 2024-03-02 | 12 |
| T5 | B1 | 2024-03-02 | 7 |

**products:**

| product_id | product_name | category |
|---|---|---|
| B1 | SQL Basics | Books |
| B2 | Data Notebook | Stationery |
| B3 | Python Guide | Books |
| B4 | Gel Pen Set | Stationery |

**Expected Output:**

| sale_date | category | total_quantity |
|---|---|---|
| 2024-03-01 | Books | 5 |
| 2024-03-01 | Stationery | 8 |
| 2024-03-02 | Books | 10 |
| 2024-03-02 | Stationery | 12 |

> **Note:** On `2024-03-02`, two sales belong to Books (B1 with qty=7 and B3 with qty=3), so their quantities are summed to 10. Each date and category combination produces one row.

---
