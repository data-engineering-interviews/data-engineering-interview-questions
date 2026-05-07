# Mortgage Rate Calculator

> **Company:** NVIDIA | **Difficulty:** Medium

---

#### Scenario

You work for a mortgage company that tracks mortgage products and which product each user has selected.

#### Task

Write a Snowflake SQL query that:
1. Joins `{{ ref("mortgage_details") }}` with `{{ ref("user_mortgages") }}` on `mortgage_id`
2. Groups the joined data by `mortgage_type`
3. Calculates `rate_of_mortgage` as `ROUND(SUM(interest_rate) / COUNT(user_id), 2)` for each group
4. Returns `mortgage_type` and `rate_of_mortgage`

#### Schema

**mortgage_details**

| Column | Type | Description |
|--------|------|-------------|
| mortgage_id | Integer | Unique identifier for the mortgage product |
| mortgage_type | String | Type of mortgage (Fixed, Variable, Adjustable, etc.) |
| interest_rate | Double | Annual interest rate for the mortgage |

**user_mortgages**

| Column | Type | Description |
|--------|------|-------------|
| user_id | String | Unique identifier for the user |
| mortgage_id | Integer | Mortgage product selected by the user |

#### Example

**mortgage_details:**

| mortgage_id | mortgage_type | interest_rate |
|---|---|---|
| 101 | Fixed | 3.75 |
| 102 | Variable | 5.20 |
| 103 | Fixed | 4.50 |
| 104 | Adjustable | 6.10 |

**user_mortgages:**

| user_id | mortgage_id |
|---|---|
| U1 | 101 |
| U2 | 101 |
| U3 | 102 |
| U4 | 103 |
| U5 | 104 |

**Expected Output:**

| mortgage_type | rate_of_mortgage |
|---|---|
| Adjustable | 6.1 |
| Fixed | 4.0 |
| Variable | 5.2 |

> **Note:** Fixed has three joined rows (U1 and U2 on mortgage 101 at 3.75, U4 on mortgage 103 at 4.50), so the rate is (3.75 + 3.75 + 4.50) / 3 = 4.0. Variable and Adjustable each have one user, so the rate equals the original interest rate.

---
