# Track Product Purchases

> **Company:** Microsoft | **Difficulty:** Hard

---

#### Scenario

You work for a retail store that tracks customer transactions and wants to understand repeat purchasing patterns.

#### Task

Write a Snowflake SQL query that:
1. For each row in `{{ ref("transactions") }}`, adds a `previous_product` column containing the `product_id` of the same customer's most recent prior transaction (ordered by `date`), or `NULL` if there is no prior transaction
2. Adds a `date_and_product` column that concatenates `date` and `previous_product` separated by a space, substituting the string `'None'` when `previous_product` is `NULL`
3. Returns all six columns: `customer_id`, `product_id`, `quantity`, `date`, `previous_product`, `date_and_product`

#### Schema

**transactions**

| Column | Type | Description |
|--------|------|-------------|
| customer_id | String | Unique identifier for the customer |
| product_id | String | Unique identifier for the purchased product |
| quantity | Integer | Number of units purchased |
| date | String | Transaction date in `YYYY-MM-DD` format |

#### Example

**transactions:**

| customer_id | product_id | quantity | date |
|---|---|---|---|
| C1 | P10 | 3 | 2024-03-01 |
| C1 | P20 | 1 | 2024-03-15 |
| C2 | P30 | 2 | 2024-04-02 |
| C1 | P30 | 5 | 2024-04-10 |
| C3 | P10 | 4 | 2024-05-01 |

**Expected Output:**

| customer_id | product_id | quantity | date | previous_product | date_and_product |
|---|---|---|---|---|---|
| C1 | P10 | 3 | 2024-03-01 | NULL | 2024-03-01 None |
| C1 | P20 | 1 | 2024-03-15 | P10 | 2024-03-15 P10 |
| C1 | P30 | 5 | 2024-04-10 | P20 | 2024-04-10 P20 |
| C2 | P30 | 2 | 2024-04-02 | NULL | 2024-04-02 None |
| C3 | P10 | 4 | 2024-05-01 | NULL | 2024-05-01 None |

> **Note:** `previous_product` resets per customer. C2 and C3 each have only one transaction, so their `previous_product` is `NULL`. The `date_and_product` column uses the literal string `'None'` when `previous_product` is `NULL`.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/track-product-purchases)
