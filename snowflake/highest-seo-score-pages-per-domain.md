# Highest SEO Score Pages per Domain

> **Company:** Cisco | **Difficulty:** Hard

---

#### Scenario

You work for an SEO analytics platform and have been given a table containing information about webpages and their SEO scores.

#### Task

Write a Snowflake SQL query that:
1. For each domain in `{{ ref("pages") }}`, finds the URL and score of the page with the highest `seo_score` (output as `highest_seo_page` and `highest_seo_score`)
2. Finds the URL and score of the single page with the highest `seo_score` across all domains (output as `overall_highest_page` and `overall_highest_score`)
3. Returns one row per domain with columns: `domain`, `highest_seo_page`, `highest_seo_score`, `overall_highest_page`, `overall_highest_score`
4. Only the domain whose best page is also the global best should have `overall_highest_page` and `overall_highest_score` populated (all other domains should have `NULL` for these columns)

#### Schema

**pages**

| Column | Type | Description |
|--------|------|-------------|
| domain | String | The domain name of the webpage |
| url | String | The full URL of the webpage |
| seo_score | Integer | The SEO score of the webpage (0 to 100) |

#### Example

**pages:**

| domain | url | seo_score |
|---|---|---|
| acme.com | https://acme.com/about | 74 |
| acme.com | https://acme.com/blog | 89 |
| acme.com | https://acme.com/contact | 65 |
| widget.io | https://widget.io/home | 91 |
| widget.io | https://widget.io/pricing | 78 |
| spark.dev | https://spark.dev/docs | 83 |
| spark.dev | https://spark.dev/faq | 70 |

**Expected Output:**

| domain | highest_seo_page | highest_seo_score | overall_highest_page | overall_highest_score |
|---|---|---|---|---|
| acme.com | https://acme.com/blog | 89 | NULL | NULL |
| spark.dev | https://spark.dev/docs | 83 | NULL | NULL |
| widget.io | https://widget.io/home | 91 | https://widget.io/home | 91 |

> **Note:** Only the domain whose best page is also the global best (`widget.io` with score 91) has `overall_highest_page` and `overall_highest_score` populated. All other domains have `NULL` for these two columns.

---
