# Math Expressions

> **Company:** IBM | **Difficulty:** Hard

---

#### Scenario

You have a table of user-submitted text entries that may or may not represent valid mathematical expressions.

#### Task

Write a Snowflake SQL query that:
1. Selects all columns from `{{ ref("expressions") }}`
2. Filters to only include rows where the `expression` column is a valid math expression (contains only digits and the operators `+`, `-`, `*`, `/`, with at least one operator separating digit groups)

#### Schema

**expressions**

| Column | Type | Description |
|--------|------|-------------|
| id | Integer | Unique identifier for each entry |
| expression | String | User-submitted text that may be a math expression |

#### Example

**expressions:**

| id | expression |
|---|---|
| 1 | 8+2 |
| 2 | hello |
| 3 | 9/3 |
| 4 | test123 |
| 5 | 4*7-1 |

**Expected Output:**

| id | expression |
|---|---|
| 1 | 8+2 |
| 3 | 9/3 |
| 5 | 4*7-1 |

> **Note:** Only rows containing digits separated by arithmetic operators (`+`, `-`, `*`, `/`) are kept. Rows with alphabetic characters or other non-matching patterns are excluded.

---
