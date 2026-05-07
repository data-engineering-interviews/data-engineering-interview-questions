# String Pattern Matching Using LIKE

> **Company:** Apple | **Difficulty:** Medium

---

#### Objective
Write an SQL query to fetch the names, department names, email addresses, and position levels of employees. The query should filter employees based on the following criteria:
- Employee names start with the letter 'A'.
- Employee email addresses contain the substring '@tech'.
- Employee position levels contain the word 'Senior'.
The results should be ordered by employee names in ascending order.

#### Additional information
- Assume the existence of two tables: `employees` and `departments`.
- The `employees` table contains the columns: `id`, `name`, `department_id`, `email`, and `position_level`.
- The `departments` table contains the columns: `id`, `name`, and `location`.
- Join the two tables on the `department_id` column from the `employees` table and the `id` column from the `departments` table.
- The results should only include columns: `name`, `department`, `email`, and `position_level`.

Constraints:
- The length of `name` will be within [1, 100].
- The length of `email` will be within [5, 100].
- The length of `position_level` will be within [5, 50].
- The number of rows in the `employees` and `departments` tables will not exceed 1000.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/string-pattern-matching-using-like)
