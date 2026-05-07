# Global & Domain SEO Leaders

> **Company:** Amazon | **Difficulty:** Hard

---

#### Objective

You are given a DataFrame containing information about webpages and their SEO (Search Engine Optimization) scores.

#### Task

Write a function that returns the pages with the highest SEO score for each domain, and also the pages with the highest SEO score among all domains. Save your result as `result_df`.

#### File Path

* Dataset: `/home/interview/pages.csv`
* Starter script: `/home/interview/seo_optimization.py`

#### Schema

**pages.csv**

| Column Name | Data Type | Description |
| --- | --- | --- |
| domain | string | The domain name of the webpage |
| url | string | The URL of the webpage |
| seo_score | integer | The SEO score of the webpage |

**Expected Output Schema**

| Column Name | Data Type | Description |
| --- | --- | --- |
| domain | string | The domain name of the webpage |
| highest_seo_page | string | The URL of the webpage with the highest SEO score within the domain |
| highest_seo_score | integer | The SEO score of the webpage with the highest SEO score within the domain |
| overall_highest_page | string | The URL of the webpage with the highest SEO score among all domains |
| overall_highest_score | double | The SEO score of the webpage with the highest SEO score among all domains |

**Constraints:**

* The input DataFrame will have at least 1 row and at most 1000 rows.
* The `seo_score` column will have values in the range of 0 to 100 (inclusive).
* The `domain` and `url` columns will have at most length 255.

#### **Example**

Given this sample input:

**pages**

| domain | url | seo_score |
| --- | --- | --- |
| example.com | [https://www.example.com/page1](https://www.example.com/page1) | 88 |
| example.com | [https://www.example.com/page2](https://www.example.com/page2) | 92 |
| example.com | [https://www.example.com/page3](https://www.example.com/page3) | 80 |
| example.net | [https://www.example.net/page1](https://www.example.net/page1) | 75 |
| example.net | [https://www.example.net/page2](https://www.example.net/page2) | 90 |
| example.org | [https://www.example.org/page1](https://www.example.org/page1) | 82 |
| example.org | [https://www.example.org/page2](https://www.example.org/page2) | 85 |

The output would be:

| domain | highest_seo_page | highest_seo_score | overall_highest_page | overall_highest_score |
| --- | --- | --- | --- | --- |
| example.com | [https://www.example.com/page2](https://www.example.com/page2) | 92 | [https://www.example.com/page2](https://www.example.com/page2) | 92.0 |
| example.net | [https://www.example.net/page2](https://www.example.net/page2) | 90 | null | null |
| example.org | [https://www.example.org/page2](https://www.example.org/page2) | 85 | null | null |

Example.com's page2 is the highest in its domain (92) and also the highest across all domains, so it fills the overall columns. Example.net and example.org have local maximums but do not match the global maximum, so their overall columns are null.

---
