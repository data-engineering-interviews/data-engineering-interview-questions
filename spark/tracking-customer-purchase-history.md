# Tracking Customer Purchase History

> **Company:** Coinbase | **Difficulty:** Hard

---

#### Objective

In a retail store, tracking customer transactions chronologically is crucial for maintaining inventory, generating sales insights, and building recommendation engines.

#### Task

Write a PySpark function that processes a `transactions` DataFrame to compute the following:

1. Add a new column called `previous_product` that contains the `product_id` of the *previous* transaction made by the same customer, in chronological order. If there is no previous transaction for a customer, this column should be null.
2. Add a new column called `date_and_product` that concatenates the transaction `date` and the `previous_product`, separated by a space. If the previous product is null, the string should literally say "None" (e.g., `"2023-01-01 None"`).

Save your result as `result_df`. Ensure the output matches the exact schema order requested.

#### File Path

* Dataset: `/home/interview/transactions.csv`
* Starter script: `/home/interview/purchase_history.py`

#### Schema

**transactions.csv**

| Column Name | Data Type |
| --- | --- |
| customer_id | string |
| product_id | string |
| quantity | integer |
| date | string |

**Expected Output Schema**

| Column Name | Data Type |
| --- | --- |
| customer_id | string |
| product_id | string |
| quantity | integer |
| date | string |
| previous_product | string |
| date_and_product | string |

#### **Example**

Given this sample input:

**transactions**

| customer_id | product_id | quantity | date |
| --- | --- | --- | --- |
| CUST1 | PROD1 | 2 | 2023-01-01 |
| CUST1 | PROD2 | 1 | 2023-01-05 |
| CUST2 | PROD3 | 5 | 2023-02-03 |
| CUST3 | PROD1 | 4 | 2023-02-07 |
| CUST1 | PROD3 | 3 | 2023-02-10 |

The output would be:

| customer_id | product_id | quantity | date | previous_product | date_and_product |
| --- | --- | --- | --- | --- | --- |
| CUST1 | PROD1 | 2 | 2023-01-01 | null | 2023-01-01 None |
| CUST1 | PROD2 | 1 | 2023-01-05 | PROD1 | 2023-01-05 PROD1 |
| CUST1 | PROD3 | 3 | 2023-02-10 | PROD2 | 2023-02-10 PROD2 |
| CUST2 | PROD3 | 5 | 2023-02-03 | null | 2023-02-03 None |
| CUST3 | PROD1 | 4 | 2023-02-07 | null | 2023-02-07 None |

---
