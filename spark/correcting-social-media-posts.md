# Correcting Social Media Posts

> **Company:** Twitter | **Difficulty:** Easy

---

#### Objective

You are working with a dataset of social media posts that contain some incorrect references that need to be corrected before publication.

#### Task

Replace every occurrence of the word "Python" with "PySpark" in the text column. Return the entire DataFrame with the same schema. Only the text column should be modified; all other columns must remain unchanged. Posts that do not contain the word "Python" should appear in the output exactly as they are in the input. Save your result as `result_df`.

#### File Path

- Dataset: `/home/interview/posts.csv`
- Starter script: `/home/interview/correct_posts.py`

#### Schema

| Column   | Type   |
|----------|--------|
| id       | int    |
| text     | string |
| date     | string |
| likes    | int    |
| comments | int    |
| shares   | int    |
| platform | string |

#### **Example**

**Input:**

| id | text                              | date       | likes | comments | shares | platform  |
|----|-----------------------------------|------------|-------|----------|--------|-----------|
| 1  | Learning Python for data science  | 2023-03-15 | 120   | 34       | 12     | Twitter   |
| 2  | Great weather today               | 2023-04-01 | 45    | 8        | 3      | Instagram |
| 3  | Python vs Java debate continues   | 2023-05-22 | 230   | 89       | 56     | LinkedIn  |

**Expected Output:**

| id | text                               | date       | likes | comments | shares | platform  |
|----|------------------------------------|------------|-------|----------|--------|-----------|
| 1  | Learning PySpark for data science  | 2023-03-15 | 120   | 34       | 12     | Twitter   |
| 2  | Great weather today                | 2023-04-01 | 45    | 8        | 3      | Instagram |
| 3  | PySpark vs Java debate continues   | 2023-05-22 | 230   | 89       | 56     | LinkedIn  |

The word "Python" in posts 1 and 3 has been replaced with "PySpark." Post 2 did not contain the word "Python," so it remains unchanged.

---
