# Anonymize User PII

> **Company:** Meta | **Difficulty:** Medium

---

#### Objective
You are working with a social media platform's user database that contains personally identifiable information (PII) which needs to be partially anonymized before sharing with the analytics team.

#### Task

Extract the domain name from each user's email address (everything after the @ symbol) and anonymize their phone number by replacing the first 6 digits with asterisks (******), keeping only the last 4 digits visible. Note that the phone number column is stored as an integer in the source data, so you will need to handle that appropriately. Your final output should contain three columns: `user_id`, `email_domain`, and `anon_phone`. Save your result as `result_df`.

#### File Path
- Dataset: `/home/interview/users.csv`
- Starter script: `/home/interview/anonymize_users.py`

#### Schema
| Column   | Type    |
|----------|---------|
| user_id  | integer |
| email    | string  |
| phone    | integer |

#### **Example**

**Input: users**

| user_id | email              | phone      |
|---------|--------------------|------------|
| 1       | alice@example.com  | 5551234567 |
| 2       | bob@company.org    | 9876543210 |

**Output:**

| user_id | email_domain | anon_phone   |
|---------|--------------|--------------|
| 1       | example.com  | ******4567   |
| 2       | company.org  | ******3210   |

The `email_domain` column contains only the part after the @ symbol. 
The `anon_phone` column replaces the first 6 digits of the phone number with asterisks, leaving the last 4 digits visible.

---
