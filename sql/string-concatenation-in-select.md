# String Concatenation in SELECT

> **Company:** Wix | **Difficulty:** Easy

---

#### Objective
Write a SQL query to retrieve the full names of all employees by combining their first and last names. The result should include a single column named `full_name`, which is the concatenation of `first_name` and `last_name` separated by a space. The output should be ordered alphabetically by `full_name`.

#### Additional information
- **Table Name:** `employees`
- **Table Schema:**

| Column | Type | Description |
|--------|------|-------------|
| id | INT | The unique identifier for each employee |
| first_name | VARCHAR | The employee's first name |
| last_name | VARCHAR | The employee's last name |

- **Output:** A list of objects with a single key `full_name`.
- **Constraints:** 
  - Ensure that `full_name` correctly combines `first_name` and `last_name` with a space in between.
  - The results must be sorted in ascending order based on `full_name`.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/string-concatenation-in-select)
