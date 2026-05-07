# Re-enrollment Rate Calculator

> **Company:** Google | **Difficulty:** Medium

---

#### Objective
Write a SQL query to calculate the re-enrollment rate of students based on their consecutive term enrollments. The re-enrollment rate is defined as the percentage of students who have enrolled in two or more consecutive terms.

#### Additional information
- Consecutive terms are identified by increasing term_ids without any gaps.
- The result should be rounded to two decimal places.
- Output the re-enrollment rate as a percentage.
- The `enrollments` table schema:

  | Column | Type |
  |--------|------|
  | student_id | INT |
  | term_id | INT |
  | course_id | VARCHAR |

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/re-enrollment-rate-calculator)
