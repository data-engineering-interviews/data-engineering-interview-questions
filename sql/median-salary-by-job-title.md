# Median Salary by Job Title

> **Company:** ActivisionBlizzard | **Difficulty:** Medium

---

#### Objective
Write an SQL query to calculate the median salary for each job title within a company. The median salary is the middle value in the list of salaries for a particular job title when the list is sorted in ascending order. If the number of salaries is even, the median is the average of the two middle numbers. Your query should return the job titles and their corresponding median salaries, rounded to two decimal places, in descending order of the median salary.

#### Additional information

The `employees` table:

| Column | Type | Description |
|--------|------|-------------|
| id | INT | The unique identifier for each employee |
| name | VARCHAR | The name of the employee |
| job_title | VARCHAR | The job title of the employee |
| salary | INT | The salary of the employee |

- Constraints:
  - The number of employees can range from 1 to 10^5.
  - The salary values are positive integers.

- Clarifications:
  - Ensure that the median salary is calculated correctly based on the number of employees for each job title.
  - The results should be sorted in descending order of the median salary.
  - If multiple job titles have the same median salary, order them alphabetically by job title.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/median-salary-by-job-title)
