# Combine Customer Orders and Products

> **Company:** Twilio | **Difficulty:** Medium

---

#### Scenario

You are working on a CRM platform that tracks customers, their orders, and the products they purchased.

#### Task

Write a Snowflake SQL query that:
1. Joins `{{ ref("orders") }}` to `{{ ref("customers") }}` on `customer_id`
2. Joins the result to `{{ ref("products") }}` on `product_id`
3. Concatenates `first_name` and `last_name` (separated by a space) as `customer_name`
4. Aliases `email` as `customer_email` and `category` as `product_category`
5. Returns only six columns: `order_id`, `customer_name`, `customer_email`, `product_name`, `product_category`, `order_date`

#### Schema

**customers**

| Column | Type | Description |
|--------|------|-------------|
| customer_id | Integer | Unique customer identifier |
| first_name | String | Customer first name |
| last_name | String | Customer last name |
| email | String | Customer email address |

**orders**

| Column | Type | Description |
|--------|------|-------------|
| order_id | Integer | Unique order identifier |
| customer_id | Integer | References customers.customer_id |
| product_id | Integer | References products.product_id |
| order_date | Date | Date the order was placed |

**products**

| Column | Type | Description |
|--------|------|-------------|
| product_id | Integer | Unique product identifier |
| product_name | String | Name of the product |
| category | String | Product category |

#### Example

**customers:**

| customer_id | first_name | last_name | email |
|---|---|---|---|
| 1 | John | Doe | john.doe@email.com |
| 2 | Jane | Smith | jane.smith@email.com |

**orders:**

| order_id | customer_id | product_id | order_date |
|---|---|---|---|
| 1001 | 1 | 101 | 2023-01-10 |
| 1002 | 2 | 102 | 2023-01-11 |

**products:**

| product_id | product_name | category |
|---|---|---|
| 101 | Product A | Category1 |
| 102 | Product B | Category2 |

**Expected Output:**

| order_id | customer_name | customer_email | product_name | product_category | order_date |
|---|---|---|---|---|---|
| 1001 | John Doe | john.doe@email.com | Product A | Category1 | 2023-01-10 |
| 1002 | Jane Smith | jane.smith@email.com | Product B | Category2 | 2023-01-11 |

> **Note:** Each order row is enriched with the customer's full name, email, and the product details by joining all three tables on their respective keys.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/combine-customer-orders-and-products)
