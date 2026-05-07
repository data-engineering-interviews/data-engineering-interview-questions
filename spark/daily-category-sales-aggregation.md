# Daily Category Sales Aggregation

> **Company:** Microsoft | **Difficulty:** Easy

---

#### Objective

You are working for an outdoor supplies company that sells various items such as camping equipment, hiking gear, fishing equipment, etc. You are given two DataFrames: `df_sales` containing daily transaction logs, and `df_products` containing the product catalog.

#### Task

Write a PySpark function that joins the two DataFrames and calculates the total quantity sold for each `product_category` on a daily basis.

Save your resulting DataFrame as `result_df`. Order the final output chronologically by `date` (ascending), and then alphabetically by `product_category` (ascending).

#### File Path

* Sales Dataset: `/home/interview/sales.csv`
* Products Dataset: `/home/interview/products.csv`
* Starter script: `/home/interview/camping_sales.py`

#### Schema

**sales.csv**

| Column Name | Type |
| --- | --- |
| sales_id | String |
| product_id | String |
| date | Date |
| quantity_sold | Integer |

**products.csv**

| Column Name | Type |
| --- | --- |
| product_id | String |
| product_name | String |
| product_category | String |

**Expected Output Schema**

| Column Name | Type |
| --- | --- |
| date | Date |
| product_category | String |
| total_quantity | Integer |

#### **Example**

Given this sample input:

**df_sales**

| sales_id | product_id | date | quantity_sold |
| --- | --- | --- | --- |
| S1 | P1 | 2023-06-01 | 10 |
| S2 | P2 | 2023-06-02 | 15 |
| S3 | P3 | 2023-06-02 | 20 |
| S4 | P4 | 2023-06-01 | 12 |
| S5 | P5 | 2023-06-03 | 25 |

**df_products**

| product_id | product_name | product_category |
| --- | --- | --- |
| P1 | Camping Tent | Camping |
| P2 | Hiking Shoes | Hiking |
| P3 | Fishing Rod | Fishing |
| P4 | Insulated Bottle | Hiking |
| P5 | Outdoor Grill | Camping |

The expected output would be:

| date | product_category | total_quantity |
| --- | --- | --- |
| 2023-06-01 | Camping | 10 |
| 2023-06-01 | Hiking | 12 |
| 2023-06-02 | Fishing | 20 |
| 2023-06-02 | Hiking | 15 |
| 2023-06-03 | Camping | 25 |

---
