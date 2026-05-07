# Calculating Overtime Pay

> **Company:** Cisco | **Difficulty:** Easy

---

#### Objective

You work in the payroll department and are asked to process the weekly payroll data for the company. You are given two DataFrames: `employees` contains employee demographic information, and `payroll` contains their logged hours and rates.


#### Task

Write a function that calculates the total pay for each employee.

The pay should be calculated as follows:

1. If an employee works less than or equal to 40 hours, their pay is the product of their hours worked and their hourly rate.
2. If an employee works more than 40 hours, they are paid the regular hourly rate for the first 40 hours, and **1.5 times** the hourly rate for any hours worked strictly above 40.

Save your result as `result_df`. **Order the final output by `employee_id` in ascending order.**

#### File Path

* Employees Dataset: `/home/interview/employees.csv`
* Payroll Dataset: `/home/interview/payroll.csv`
* Starter script: `/home/interview/run_payroll.py`

#### Schema

**employees.csv**

| Column Name | Data Type |
| --- | --- |
| employee_id | integer |
| name | string |
| age | integer |
| position | string |

**payroll.csv**

| Column Name | Data Type |
| --- | --- |
| employee_id | integer |
| hours_worked | float |
| hourly_rate | float |

**Expected Output Schema**

| Column Name | Data Type |
| --- | --- |
| employee_id | integer |
| name | string |
| position | string |
| pay | float |

#### **Example**

Given this sample input:

**employees**


| employee_id | name | age | position |
| --- | --- | --- | --- |
| 1 | Alice | 30 | Software Engineer |
| 2 | Bob | 28 | Data Analyst |
| 3 | Carol | 35 | Product Manager |
| 4 | Dave | 26 | Software Engineer |

**payroll**

| employee_id | hours_worked | hourly_rate |
| --- | --- | --- |
| 1 | 45.0 | 30.0 |
| 2 | 38.0 | 25.0 |
| 3 | 41.5 | 35.0 |
| 4 | 40.0 | 28.0 |

The output would be:

| employee_id | name | pay | position |
| --- | --- | --- | --- |
| 1 | Alice | 1425.00 | Software Engineer |
| 2 | Bob | 950.00 | Data Analyst |
| 3 | Carol | 1478.75 | Product Manager |
| 4 | Dave | 1120.00 | Software Engineer |

*Explanation:* * Alice worked 45 hours. Her first 40 hours are at $30.00 ($1200). Her remaining 5 hours are at 1.5x rate ($45.00), equating to $225. Total: $1425.00.

* Bob worked exactly 38 hours at $25.00, resulting in $950.00.

---
