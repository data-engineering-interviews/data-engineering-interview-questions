# Filter Popular Videos on a Streaming Platform

> **Company:** Apple | **Difficulty:** Easy

---

#### Scenario

You work at a video streaming company and have been given a table containing information about videos on the platform.

#### Task

Write a Snowflake SQL query that:
1. Selects all columns from `{{ ref("videos") }}`
2. Filters to only include videos with more than 1,000,000 views
3. Filters to only include videos released in 2019 or later

#### Schema

**videos**

| Column | Type | Description |
|--------|------|-------------|
| video_id | Integer | Unique video identifier |
| title | String | Video title |
| genre | String | Video genre |
| release_year | Integer | Year of release |
| duration | Integer | Duration in minutes |
| view_count | Integer | Total view count |

#### Example

**videos:**

| video_id | title | genre | release_year | duration | view_count |
|---|---|---|---|---|---|
| 1 | Amazing Adventure | Action | 2020 | 120 | 2500000 |
| 2 | Sci-fi World | Sci-fi | 2018 | 140 | 800000 |
| 3 | Mysterious Island | Drama | 2022 | 115 | 1500000 |
| 4 | Old Classic | Drama | 2016 | 130 | 3200000 |
| 5 | New Horizons | Sci-fi | 2021 | 128 | 500000 |

**Expected Output:**

| video_id | title | genre | release_year | duration | view_count |
|---|---|---|---|---|---|
| 1 | Amazing Adventure | Action | 2020 | 120 | 2500000 |
| 3 | Mysterious Island | Drama | 2022 | 115 | 1500000 |

> **Note:** Video 2 is excluded (under 1,000,000 views), Video 4 is excluded (released before 2019), Video 5 is excluded (under 1,000,000 views).

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/filter-popular-videos-on-a-streaming-platform)
