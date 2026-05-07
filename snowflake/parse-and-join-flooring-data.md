# Flooring Company Data

> **Company:** Databricks | **Difficulty:** Medium

---

#### Scenario

You work as a data analyst for a flooring company and have three tables containing customer, order, and product information.

#### Task

Write a Snowflake SQL query that:
1. Joins `{{ ref("orders") }}` to `{{ ref("customers") }}` on `customer_id` and to `{{ ref("products") }}` on `product_id` using inner joins
2. Splits the `full_name` column (space-separated) into `first_name` and `last_name`
3. Splits the `product_info` column (comma-separated) into `product_type` and `product_color`
4. Returns these 9 columns: `order_id`, `customer_id`, `first_name`, `last_name`, `location`, `product_id`, `product_type`, `product_color`, `quantity`

#### Schema

**customers**

| Column | Type | Description |
|--------|------|-------------|
| customer_id | Integer | Unique customer identifier |
| full_name | String | First and last name separated by a space |
| location | String | Customer location |

**orders**

| Column | Type | Description |
|--------|------|-------------|
| order_id | Integer | Unique order identifier |
| customer_id | Integer | Foreign key to customers |
| product_id | Integer | Foreign key to products |
| quantity | Integer | Number of units ordered |

**products**

| Column | Type | Description |
|--------|------|-------------|
| product_id | Integer | Unique product identifier |
| product_info | String | Product type and color separated by a comma |

#### Example

**customers:**

| customer_id | full_name | location |
|---|---|---|
| 1 | Maria Lopez | Denver |
| 2 | Tom Baker | Seattle |
| 3 | Nina Patel | Austin |
| 4 | Carl Reed | Miami |
| 5 | Sue Wang | Portland |

**orders:**

| order_id | customer_id | product_id | quantity |
|---|---|---|---|
| 501 | 1 | 301 | 4 |
| 502 | 2 | 302 | 7 |
| 503 | 3 | 303 | 2 |
| 504 | 4 | 304 | 5 |
| 505 | 5 | 305 | 3 |

**products:**

| product_id | product_info |
|---|---|
| 301 | Hardwood,Walnut |
| 302 | Tile,Ivory |
| 303 | Vinyl,Slate |
| 304 | Carpet,Beige |
| 305 | Laminate,Oak |

**Expected Output:**

| order_id | customer_id | first_name | last_name | location | product_id | product_type | product_color | quantity |
|---|---|---|---|---|---|---|---|---|
| 501 | 1 | Maria | Lopez | Denver | 301 | Hardwood | Walnut | 4 |
| 502 | 2 | Tom | Baker | Seattle | 302 | Tile | Ivory | 7 |
| 503 | 3 | Nina | Patel | Austin | 303 | Vinyl | Slate | 2 |
| 504 | 4 | Carl | Reed | Miami | 304 | Carpet | Beige | 5 |
| 505 | 5 | Sue | Wang | Portland | 305 | Laminate | Oak | 3 |

> **Note:** `full_name` is split on the space into `first_name` and `last_name`. `product_info` is split on the comma into `product_type` and `product_color`. Only orders with matching customers and products appear in the output.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/parse-and-join-flooring-data)
