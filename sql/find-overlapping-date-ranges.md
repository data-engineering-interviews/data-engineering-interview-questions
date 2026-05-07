# Find Overlapping Date Ranges

> **Company:** X | **Difficulty:** Medium

---

#### Objective
Write a SQL query to identify all project assignments where an employee is allocated to multiple projects with overlapping timeframes. The result should include the project ID, employee ID, start date, and end date of each such assignment. Ensure that the output is ordered by project ID and employee ID.

#### Additional information
- You are provided with a table named `assignments` with the following columns:

| Column | Type | Description |
|--------|------|-------------|
| project_id | INTEGER | The unique identifier for each project |
| employee_id | INTEGER | The unique identifier for each employee |
| start_date | DATE | The start date of the employee's assignment to the project |
| end_date | DATE | The end date of the employee's assignment to the project |

- An employee has overlapping assignments if they are assigned to different projects where the date ranges intersect. Specifically, two assignments overlap if:
  - The projects are different (`project_id` differs).
  - The start date of one assignment is on or before the end date of the other assignment.
  - The end date of one assignment is on or after the start date of the other assignment.

- The query should return distinct records without duplicates.

- Order the final result set first by `project_id` in ascending order and then by `employee_id` in ascending order.

- Assume that all dates are valid and `start_date` is always on or before `end_date` for each assignment.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/find-overlapping-date-ranges)
