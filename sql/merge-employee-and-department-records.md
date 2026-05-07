# Merge Employee and Department Records

> **Company:** Anthropic | **Difficulty:** Hard

---

#### Objective
Write a SQL query to find employees whose salaries are above the average salary of their respective departments. The departments should have more than 10 employees. For each qualifying employee, return their name, department name, salary, average salary of the department, and the count of employees in the department who earn more than $75,000. The results should be ordered by department name and salary in descending order.

#### Additional information
- Ensure that the departments have more than 10 employees.
- The average salary should be rounded to 2 decimal places.
- The query should also count how many employees in each department earn more than $75,000.
- The results should include columns: employee_name, department_name, salary, dept_avg_salary, and high_earners.

Constraints:
- You can assume that
- The `employees` table contains the columns: `id`, `name`, `department_id`, and `salary`.
- You can assume that
- The `departments` table contains the columns: `id` and `name`.
- The query should be efficient and handle large datasets within reasonable time limits.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/merge-employee-and-department-records)
