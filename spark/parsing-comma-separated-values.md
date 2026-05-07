# Parsing Comma-Separated Values

> **Company:** Revolut | **Difficulty:** Medium

---

#### Objective

A background check company has a database of the checks they have performed. They want to process this data for further analysis. You are given a DataFrame `background_checks` that stores these checks.


#### Task

The `criminal_record`, `employment_history`, `education_history` and `address` fields are comma-separated varchar fields that hold multiple pieces of information.

Write a PySpark function that transforms the `background_checks` DataFrame to count the number of items in each of those comma-separated fields. Create the following new columns:

* `crime_count`: The count of crimes in the `criminal_record` column.
* `jobs_count`: The count of jobs in the `employment_history` column.
* `degrees_count`: The count of degrees in the `education_history` column.
* `places_lived_count`: The count of addresses in the `address` column.

Save your resulting DataFrame as `result_df`. Ensure the output exactly matches the requested Output Schema, and **order the final output by `check_id` in ascending order.**


#### File Path

* Background Checks Dataset: `/home/interview/background_checks.csv`
* Starter script: `/home/interview/parse_checks.py`

#### Schema

**background_checks.csv**

| Column Name | Data Type |
| --- | --- |
| check_id | Integer |
| full_name | String |
| dob | Date |
| criminal_record | String |
| employment_history | String |
| education_history | String |
| address | String |

**Expected Output Schema**

| Column Name | Data Type |
| --- | --- |
| check_id | Integer |
| full_name | String |
| dob | Date |
| crime_count | Integer |
| jobs_count | Integer |
| degrees_count | Integer |
| places_lived_count | Integer |

#### **Example**

Given this sample input:

**background_checks**

| check_id | full_name | dob | criminal_record | employment_history | education_history | address |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | John Doe | 1980-05-05 | Theft,Assault | ABC Corp,XYZ Corp | B.A. in English,M.A. in English | 123 Main St,456 Pine St |
| 2 | Jane Smith | 1982-07-12 | DUI | DEF Corp,GHI Corp,JKL Corp | B.Sc. in Physics | 789 Oak St |
| 3 | Bob Johnson | 1975-10-20 | Theft,Fraud,Embezzlement | MNO Corp | B.A. in History,M.A. in History | 321 Cedar St,654 Elm St |

The expected output would be:

| check_id | full_name | dob | crime_count | jobs_count | degrees_count | places_lived_count |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | John Doe | 1980-05-05 | 2 | 2 | 2 | 2 |
| 2 | Jane Smith | 1982-07-12 | 1 | 3 | 1 | 1 |
| 3 | Bob Johnson | 1975-10-20 | 3 | 1 | 2 | 2 |

---
