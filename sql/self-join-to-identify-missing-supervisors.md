# Self-Join to Identify Missing Supervisors

> **Company:** Meta | **Difficulty:** Easy

---

#### Objective
Write a SQL query to identify employees whose supervisors are not present in the employee database. The query should return the employee's ID, name, and their supervisor's ID, sorted by the employee's ID.

#### Additional information
- You have a table named `employees` with the following columns: `employee_id`, `name`, and `supervisor_id`.
- An employee with a `supervisor_id` equal to `null` means they do not have a supervisor.
- The output should only include employees where the `supervisor_id` is not present in the `employee_id` column of any record.
- The output should be sorted by `employee_id` in ascending order.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/self-join-to-identify-missing-supervisors)
