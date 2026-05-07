# Venture Capital Sector Analysis

> **Company:** Cloudflare | **Difficulty:** Medium

---

#### Objective

You are given two DataFrames related to venture capital investments. The `companies` DataFrame lists startups and their associated industries, and the `investments` DataFrame logs individual funding rounds.

#### Task

Write a PySpark function that calculates the total investment amount injected into each industry sector. Your final result must be sorted by `total_investment` in **descending order** so the highest-funded industries appear at the top.

Save your result as `result_df`.

#### File Path

* Companies Dataset: `/home/interview/companies.csv`
* Investments Dataset: `/home/interview/investments.csv`
* Starter script: `/home/interview/vc_analysis.py`

#### Schema

**companies.csv**

| Column Name | Data Type |
| --- | --- |
| company_id | integer |
| company_name | string |
| industry | string |

**investments.csv**

| Column Name | Data Type |
| --- | --- |
| investment_id | integer |
| company_id | integer |
| amount | double |

**Expected Output Schema**

| Column Name | Data Type |
| --- | --- |
| industry | string |
| total_investment | double |

#### **Example**

Given this sample input:

**companies**

| company_id | company_name | industry |
| --- | --- | --- |
| 1 | AlphaTech | Technology |
| 2 | BetaHealth | Healthcare |
| 3 | GammaEntertainment | Entertainment |
| 4 | DeltaGreen | Renewable Energy |
| 5 | EpsilonFinance | Finance |

**investments**

| investment_id | company_id | amount |
| --- | --- | --- |
| 1 | 1 | 5000000.0 |
| 2 | 2 | 3000000.0 |
| 3 | 3 | 1000000.0 |
| 4 | 4 | 4000000.0 |
| 5 | 5 | 2000000.0 |

The output would be:

| industry | total_investment |
| --- | --- |
| Technology | 5000000.0 |
| Renewable Energy | 4000000.0 |
| Healthcare | 3000000.0 |
| Finance | 2000000.0 |
| Entertainment | 1000000.0 |

*(Note: The output is sorted by total_investment in descending order).*

---
