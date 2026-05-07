# Join Employees and Departments

> **Company:** Adobe | **Difficulty:** Easy

---

#### Objective
Write an SQL query to retrieve a list of employees who earn more than $50,000. For each qualifying employee, display their ID, first name, last name, job title, hire date, and the name of their department. If an employee is not assigned to any department, the department name should be shown as `NULL`. The resulting list should be ordered by the hire date in descending order, showing the most recently hired employees first.

#### Additional information
- **Tables:**

  The `employees` table:

  | Column | Type | Description |
  |--------|------|-------------|
  | employee_id | Integer | Unique identifier for each employee |
  | first_name | String | Employee's first name |
  | last_name | String | Employee's last name |
  | department_id | Integer | Identifier for the department the employee belongs to. This can be `NULL` if the employee is not assigned to any department |
  | job_title | String | Title of the employee's job |
  | salary | Integer | Employee's salary |
  | hire_date | Date | Date the employee was hired |

  The `departments` table:

  | Column | Type | Description |
  |--------|------|-------------|
  | department_id | Integer | Unique identifier for each department |
  | department_name | String | Name of the department |
  | location | String | Location of the department |

- **Requirements:**
  - Use a `LEFT JOIN` to combine `employees` and `departments` based on `department_id`.
  - Filter the employees to include only those with a `salary` greater than 50000.
  - The `department_name` should appear as `NULL` for employees without an associated department.
  - Order the results by `hire_date` in descending order.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/join-employees-and-departments)
