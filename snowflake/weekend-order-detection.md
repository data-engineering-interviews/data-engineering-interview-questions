# Weekend Order Detection

> **Company:** IBM | **Difficulty:** Medium

---

#### Scenario

You work for an e-commerce company and have been given two tables containing order records (with dates in `MM/DD/YYYY` format) and product details.

#### Task

Write a Snowflake SQL query that:
1. Joins `{{ ref("orders") }}` with `{{ ref("products") }}` on `product_id` using an `INNER JOIN`
2. Parses `order_date` from `MM/DD/YYYY` format using `TRY_TO_DATE` to handle invalid dates gracefully
3. Drops rows where `order_date` is invalid (where `TRY_TO_DATE` returns `NULL`)
4. Adds an `is_weekend` column that is `TRUE` when the parsed date falls on Saturday or Sunday, using `DAYOFWEEK`
5. Returns `user_id`, `product_name`, `category`, the original `order_date` string, and `is_weekend`

#### Schema

**orders**

| Column | Type | Description |
|--------|------|-------------|
| order_id | Integer | Unique identifier for the order |
| product_id | String | Identifier for the product ordered |
| user_id | String | Identifier for the user who placed the order |
| order_date | String | Date of order placement in `MM/DD/YYYY` format |

**products**

| Column | Type | Description |
|--------|------|-------------|
| product_id | String | Unique identifier for the product |
| product_name | String | Name of the product |
| category | String | Product category |

#### Example

**orders:**

| order_id | product_id | user_id | order_date |
|---|---|---|---|
| 1 | P001 | U101 | 01/07/2024 |
| 2 | P002 | U101 | 01/10/2024 |
| 3 | P001 | U102 | 01/13/2024 |
| 4 | P003 | U102 | 01/15/2024 |
| 5 | P004 | U103 | 01/21/2024 |
| 6 | P002 | U103 | 99/99/9999 |

**products:**

| product_id | product_name | category |
|---|---|---|
| P001 | Wireless Mouse | Electronics |
| P002 | Cotton T-Shirt | Clothing |
| P003 | Scented Candle | Home Goods |
| P004 | Python Cookbook | Books |

**Expected Output:**

| user_id | product_name | category | order_date | is_weekend |
|---|---|---|---|---|
| U101 | Wireless Mouse | Electronics | 01/07/2024 | true |
| U101 | Cotton T-Shirt | Clothing | 01/10/2024 | false |
| U102 | Wireless Mouse | Electronics | 01/13/2024 | true |
| U102 | Scented Candle | Home Goods | 01/15/2024 | false |
| U103 | Python Cookbook | Books | 01/21/2024 | true |

> **Note:** Row with order_date `99/99/9999` is dropped because it is not a valid date. 01/07/2024 (Sunday), 01/13/2024 (Saturday), and 01/21/2024 (Sunday) are weekends. 01/10/2024 (Wednesday) and 01/15/2024 (Monday) are weekdays.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/weekend-order-detection)
