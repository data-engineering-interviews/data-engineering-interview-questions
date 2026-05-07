# Replace Keywords in Social Media Post Text

> **Company:** PayPal | **Difficulty:** Easy

---

#### Scenario

You work for a social media analytics company and have been given a table containing information about social media posts across multiple platforms.

#### Task

Write a Snowflake SQL query that:
1. Selects all columns from `{{ ref("social_media") }}`
2. Replaces every occurrence of `"Python"` in the `text` column with `"PySpark"`
3. Returns the same 7 columns as the input (preserving the original column names)

#### Schema

**social_media**

| Column | Type | Description |
|--------|------|-------------|
| id | Integer | Unique identifier for each post |
| text | String | Text content of the social media post |
| date | String | Date the post was made (YYYY-MM-DD format) |
| likes | Integer | Number of likes the post received |
| comments | Integer | Number of comments the post received |
| shares | Integer | Number of shares the post received |
| platform | String | Platform where the post was made (e.g. Twitter, Facebook, Instagram) |

#### Example

**social_media:**

| id | text | date | likes | comments | shares | platform |
|---|---|---|---|---|---|---|
| 1 | This is a Python post. | 2022-03-01 | 10 | 3 | 2 | Twitter |
| 2 | Another post about Python. | 2022-03-02 | 20 | 5 | 3 | Instagram |
| 3 | Python is great for data analysis. | 2022-03-03 | 30 | 2 | 4 | Facebook |

**Expected Output:**

| id | text | date | likes | comments | shares | platform |
|---|---|---|---|---|---|---|
| 1 | This is a PySpark post. | 2022-03-01 | 10 | 3 | 2 | Twitter |
| 2 | Another post about PySpark. | 2022-03-02 | 20 | 5 | 3 | Instagram |
| 3 | PySpark is great for data analysis. | 2022-03-03 | 30 | 2 | 4 | Facebook |

> **Note:** Every occurrence of "Python" in the text column is replaced with "PySpark". All other columns remain unchanged.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/replace-keywords-in-social-media-post-text)
