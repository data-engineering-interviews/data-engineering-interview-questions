# Salary Comparison with CTE Aggregation

> **Company:** Crypto.Com | **Difficulty:** Medium

---

#### Objective
Write an SQL query to find employees whose salaries are above the average salary of their respective departments. The query should return the employee's name, department name, employee's salary, and the average salary of the department rounded to two decimal places. The results should be ordered by department name and then by employee salary in descending order.

#### Additional information
- Each department has a unique ID.
- Each employee belongs to only one department.
- The output should include only those employees who earn more than the average salary of their department.
- The salary values should be rounded to two decimal places in the output.
- The results must be sorted first by department name in ascending order, then by employee salary in descending order.

Constraints:
- The number of employees will be between 1 and 10^4.
- The number of departments will be between 1 and 10^3.

Clarifications:
- You can assume that the department names and employee names are unique within their respective tables.
- Locations of the departments are not relevant for this query.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/salary-comparison-with-cte-aggregation)
