# Merge Customer Records from Two Sources

> **Company:** Lyft | **Difficulty:** Easy

---

#### Scenario

A rideshare company maintains customer records in two separate regional tables that share the same schema.

#### Task

Write a Snowflake SQL query that:
1. Selects all columns from `{{ ref("customers_west") }}`
2. Selects all columns from `{{ ref("customers_east") }}`
3. Returns all rows from both tables combined (including any duplicates)

#### Schema

**customers_west**

| Column | Type | Description |
|--------|------|-------------|
| customer_id | Integer | Unique customer identifier |
| first_name | String | Customer first name |
| last_name | String | Customer last name |
| age | Integer | Customer age |
| plan_type | String | Subscription plan (basic, plus, premium) |

**customers_east**

| Column | Type | Description |
|--------|------|-------------|
| customer_id | Integer | Unique customer identifier |
| first_name | String | Customer first name |
| last_name | String | Customer last name |
| age | Integer | Customer age |
| plan_type | String | Subscription plan (basic, plus, premium) |

#### Example

**customers_west:**

| customer_id | first_name | last_name | age | plan_type |
|---|---|---|---|---|
| 1 | Liam | Carter | 28 | basic |
| 2 | Mia | Reeves | 34 | plus |
| 3 | Noah | Foster | 41 | premium |

**customers_east:**

| customer_id | first_name | last_name | age | plan_type |
|---|---|---|---|---|
| 4 | Zara | Patel | 26 | basic |
| 5 | Ethan | Brooks | 52 | plus |

**Expected Output:**

| customer_id | first_name | last_name | age | plan_type |
|---|---|---|---|---|
| 1 | Liam | Carter | 28 | basic |
| 2 | Mia | Reeves | 34 | plus |
| 3 | Noah | Foster | 41 | premium |
| 4 | Zara | Patel | 26 | basic |
| 5 | Ethan | Brooks | 52 | plus |

> **Note:** All rows from both tables appear in the output. The combined result contains 5 rows (3 from west + 2 from east).

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/merge-customer-records-from-two-sources)
