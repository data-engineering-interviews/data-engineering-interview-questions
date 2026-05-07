# Anonymize User PII Data for a Social Media Platform

> **Company:** Atlassian | **Difficulty:** Medium

---

#### Scenario

A social media company stores user information including email addresses and phone numbers, and needs to protect user privacy before sharing the data.

#### Task

Write a Snowflake SQL query that:
1. Reads from `{{ ref("input_df") }}`
2. Extracts the domain name from the `email` column (everything after the `@` symbol) and aliases it as `email_domain`
3. Anonymizes the `phone` column by replacing the first 6 digits with asterisks (`******`) and keeping the last 4 digits, aliased as `anon_phone`
4. Returns `user_id`, `email_domain`, and `anon_phone`

#### Schema

**input_df**

| Column | Type | Description |
|--------|------|-------------|
| user_id | Integer | Unique user identifier |
| email | String | User email address |
| phone | Integer | 10-digit phone number |

#### Example

**input_df:**

| user_id | email | phone |
|---|---|---|
| 1 | alice@example.com | 5551234567 |
| 2 | bob@domain.net | 5559876543 |
| 3 | carol@email.org | 5551239876 |
| 4 | dave@site.com | 5554567890 |
| 5 | eve@platform.io | 5559871234 |

**Expected Output:**

| user_id | email_domain | anon_phone |
|---|---|---|
| 1 | example.com | ******4567 |
| 2 | domain.net | ******6543 |
| 3 | email.org | ******9876 |
| 4 | site.com | ******7890 |
| 5 | platform.io | ******1234 |

> **Note:** The email domain is the portion after the `@` symbol. The phone is masked so that only the last 4 digits are visible.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/anonymize-user-pii-data-for-a-social-media-platform)
