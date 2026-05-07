# Products and Duplicates

> **Company:** JPMorgan | **Difficulty:** Medium

---

#### Scenario

You work for a manufacturing company that tracks products and their associated manufacturing processes, but both datasets contain duplicate rows due to data quality issues.

#### Task

Write a Snowflake SQL query that:
1. Removes duplicate rows from `{{ ref("products") }}` using `SELECT DISTINCT` or a `ROW_NUMBER` window function
2. Removes duplicate rows from `{{ ref("manufacturing") }}` in the same way
3. Joins the deduplicated results on `product_id` using an `INNER JOIN`
4. Returns these columns in order: `product_id`, `product_name`, `category`, `process_id`, `process_name`, `duration`

#### Schema

**products**

| Column | Type | Description |
|--------|------|-------------|
| product_id | Integer | Unique identifier for each product |
| product_name | String | Name of the product |
| category | String | Product category |

**manufacturing**

| Column | Type | Description |
|--------|------|-------------|
| process_id | Integer | Unique identifier for each manufacturing process |
| product_id | Integer | Identifier linking the process to a product |
| process_name | String | Name of the manufacturing process |
| duration | Float | Duration of the process in hours |

#### Example

**products** (note the duplicate row for product_id 1):

| product_id | product_name | category |
|---|---|---|
| 1 | Bolt M6 | Fasteners |
| 2 | Hinge L | Hardware |
| 3 | Spring K | Components |
| 4 | Gasket R | Seals |
| 1 | Bolt M6 | Fasteners |

**manufacturing:**

| process_id | product_id | process_name | duration |
|---|---|---|---|
| 501 | 1 | Stamping | 1.2 |
| 502 | 2 | Bending | 2.4 |
| 503 | 3 | Coiling | 1.8 |
| 504 | 4 | Molding | 3.0 |
| 505 | 1 | Polishing | 0.8 |

**Expected Output:**

| product_id | product_name | category | process_id | process_name | duration |
|---|---|---|---|---|---|
| 1 | Bolt M6 | Fasteners | 501 | Stamping | 1.2 |
| 1 | Bolt M6 | Fasteners | 505 | Polishing | 0.8 |
| 2 | Hinge L | Hardware | 502 | Bending | 2.4 |
| 3 | Spring K | Components | 503 | Coiling | 1.8 |
| 4 | Gasket R | Seals | 504 | Molding | 3.0 |

> **Note:** The duplicate row for product_id 1 in `products` must be removed before joining. Without deduplication, Bolt M6 would appear twice per process, producing incorrect results.

---
