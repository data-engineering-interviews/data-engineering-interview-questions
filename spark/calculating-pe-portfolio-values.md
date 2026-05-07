# Calculating PE Portfolio Values

> **Company:** IBM | **Difficulty:** Medium

---

#### Objective

You work for a Private Equity (PE) Firm and are given two DataFrames: `portfolio`, which contains the companies that a private equity firm holds, and `prices`, which contains the daily price movements for the equities.

#### Task

Write a PySpark function to merge these two datasets and compute the total daily portfolio value for each private equity firm.

To find the daily portfolio value, you must multiply the number of `shares` a firm holds in a company by the `closing_price` of that company on a specific date, and then sum those values up for the entire firm.

Save your resulting DataFrame as `result_df`. Ensure the output strictly matches the requested Output Schema, casting the final `portfolio_value` to an `Integer`. Order the output alphabetically by `PE_firm`, and then chronologically by `date`.

#### File Path

* Portfolio Dataset: `/home/interview/portfolio.csv`
* Prices Dataset: `/home/interview/prices.csv`
* Starter script: `/home/interview/portfolio_values.py`

#### Schema

**portfolio.csv**

| Column Name | Data Type | Description |
| --- | --- | --- |
| PE_firm | String | The name of the private equity firm |
| company | String | The name of the company |
| shares | Integer | The number of shares the firm holds in the company |

**prices.csv**

| Column Name | Data Type | Description |
| --- | --- | --- |
| date | Date | The date |
| company | String | The name of the company |
| closing_price | Double | The closing price of the company's equity on the date |

**Expected Output Schema**

| Column Name | Data Type | Description |
| --- | --- | --- |
| PE_firm | String | The name of the private equity firm |
| date | Date | The date |
| portfolio_value | Integer | The daily portfolio value of the private equity firm |

#### **Example**

Given this sample input:

**portfolio**

| PE_firm | company | shares |
| --- | --- | --- |
| Alpha | A | 1000 |
| Alpha | B | 2000 |
| Beta | A | 1500 |
| Beta | C | 2500 |
| Gamma | B | 1200 |
| Gamma | C | 1300 |

**prices**

| date | company | closing_price |
| --- | --- | --- |
| 2023-01-01 | A | 50.0 |
| 2023-01-01 | B | 20.0 |
| 2023-01-01 | C | 30.0 |
| 2023-01-02 | A | 52.0 |
| 2023-01-02 | B | 21.0 |
| 2023-01-02 | C | 31.0 |

The expected output would be:

| PE_firm | date | portfolio_value |
| --- | --- | --- |
| Alpha | 2023-01-01 | 90000 |
| Alpha | 2023-01-02 | 94000 |
| Beta | 2023-01-01 | 150000 |
| Beta | 2023-01-02 | 155500 |
| Gamma | 2023-01-01 | 63000 |
| Gamma | 2023-01-02 | 65500 |

---
