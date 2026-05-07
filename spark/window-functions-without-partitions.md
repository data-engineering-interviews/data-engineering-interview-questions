# Window Functions without Partitions

> **Company:** Google | **Difficulty:** Medium

---

#### Objective

A manufacturing company is analyzing its production process and organizing its inventory. You are provided with two DataFrames: `df1` contains the manufacturing logs and locations, while `df2` contains the product catalog details.



#### Task

Write a PySpark function that joins both DataFrames on the `product_id`. After joining, create a new column named `row_number` which assigns a unique serial number to each row in ascending order of the `manufacturing_date`. **If two dates are identical, use `product_id` (ascending) as a tie-breaker to ensure row numbers are assigned consistently.**

The `row_number` should start from 1 and increment by 1 for every subsequent row. Save your resulting DataFrame as `result_df`. Ensure the output matches the exact schema order requested, and **order the final output by the newly created `row_number` column.**

#### File Path

* Manufacturing Logs: `/home/interview/df1.csv`
* Product Catalog: `/home/interview/df2.csv`
* Starter script: `/home/interview/organize_parts.py`

#### Schema

**df1.csv**

| Column Name | Data Type |
| --- | --- |
| product_id | String |
| manufacturing_date | Date |
| manufacturing_location | String |

**df2.csv**

| Column Name | Data Type |
| --- | --- |
| product_id | String |
| product_name | String |
| product_type | String |

**Expected Output Schema**

| Column Name | Data Type |
| --- | --- |
| product_id | String |
| manufacturing_date | Date |
| manufacturing_location | String |
| product_name | String |
| product_type | String |
| row_number | Integer |

#### **Example**

Given this sample input:

**df1**

| product_id | manufacturing_date | manufacturing_location |
| --- | --- | --- |
| P1 | 2023-01-01 | Location_A |
| P2 | 2023-01-02 | Location_B |
| P3 | 2023-01-03 | Location_C |

**df2**

| product_id | product_name | product_type |
| --- | --- | --- |
| P1 | Widget_A | Widget |
| P2 | Gadget_B | Gadget |
| P3 | Device_C | Device |

The expected output would be:

| product_id | manufacturing_date | manufacturing_location | product_name | product_type | row_number |
| --- | --- | --- | --- | --- | --- |
| P1 | 2023-01-01 | Location_A | Widget_A | Widget | 1 |
| P2 | 2023-01-02 | Location_B | Gadget_B | Gadget | 2 |
| P3 | 2023-01-03 | Location_C | Device_C | Device | 3 |

---
