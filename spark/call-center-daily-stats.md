# Call Center Daily Stats

> **Company:** VMware | **Difficulty:** Medium

---


#### Objective

You are working with call center data where individual call records and customer information are stored in separate tables.

#### Task

Join the calls table with the customers table on `cust_id` to enrich each call record with customer details. Then group the joined data by `date` to compute two metrics for each date: the number of distinct customers who made calls and the total duration of all calls. Note that a single customer may place multiple calls on the same day, but they should only be counted once toward the distinct customer count. Your output should contain three columns: `date`, `num_customers`, and `total_duration`. Save your result as `result_df`.

#### File Path

- Calls: `/home/interview/calls.csv`
- Customers: `/home/interview/customers.csv`
- Starter script: `/home/interview/call_center_stats.py`

#### Schema

**calls.csv**

| Column   | Type    |
|----------|---------|
| call_id  | integer |
| cust_id  | integer |
| date     | string  |
| duration | integer |

**customers.csv**

| Column  | Type    |
|---------|---------|
| cust_id | integer |
| name    | string  |
| state   | string  |

**Expected output schema**

| Column         | Type    |
|----------------|---------|
| date           | string  |
| num_customers  | integer |
| total_duration | integer |

#### **Example**

Given this sample input:

**calls**

| call_id | cust_id | date       | duration |
|---------|---------|------------|----------|
| 1       | 101     | 2024-03-01 | 120      |
| 2       | 102     | 2024-03-01 | 300      |
| 3       | 101     | 2024-03-01 | 200      |
| 4       | 103     | 2024-03-02 | 150      |
| 5       | 101     | 2024-03-02 | 400      |

**customers**

| cust_id | name       | state |
|---------|------------|-------|
| 101     | Alice Wong | CA    |
| 102     | Bob Smith  | TX    |
| 103     | Carol Lee  | NY    |

The output would be:

| date       | num_customers | total_duration |
|------------|---------------|----------------|
| 2024-03-01 | 2             | 620            |
| 2024-03-02 | 2             | 550            |

On 2024-03-01, customer 101 made two calls (120 + 200) and customer 102 made one call (300). Even though there are three call records, only two distinct customers called, so `num_customers` is 2 and `total_duration` is 620. On 2024-03-02, customers 103 and 101 each made one call, giving 2 distinct customers and a total duration of 550.

---
