# Filter Popular Videos

> **Company:** Netflix | **Difficulty:** Medium

---

#### Objective

You work at a video streaming company and have been given a DataFrame containing information about videos on the platform. 


#### Task

Filter the DataFrame to keep only videos that have more than 1,000,000 views and were released in 2019 or later. Save your filtered result as `result_df`. The starter script will handle writing it to the output path.

#### File Path

- Dataset:  `/home/interview/videos.csv` 
- Starter script: `/home/interview/filter_videos.py` 

#### Schema

| Column       | Type    |
|--------------|---------|
| video_id     | integer |
| title        | string  |
| genre        | string  |
| release_year | integer |
| duration     | integer |
| view_count   | integer |



#### **Example**

Given this sample input:

| video_id | title             | genre  | release_year | duration | view_count |
|----------|-------------------|--------|--------------|----------|------------|
| 1        | Amazing Adventure | Action | 2020         | 120      | 2500000    |
| 2        | Sci-fi World      | Sci-fi | 2018         | 140      | 800000     |
| 3        | Mysterious Island | Drama  | 2022         | 115      | 1500000    |
| 4        | Old Classic       | Drama  | 2016         | 130      | 3200000    |
| 5        | New Horizons      | Sci-fi | 2021         | 128      | 500000     |

The filtered output would contain:

| video_id | title             | genre  | release_year | duration | view_count |
|----------|-------------------|--------|--------------|----------|------------|
| 1        | Amazing Adventure | Action | 2020         | 120      | 2500000    |
| 3        | Mysterious Island | Drama  | 2022         | 115      | 1500000    |

Video 2 is excluded (under 1,000,000 views)
Video 4 is excluded (released before 2019)
Video 5 is excluded (under 1,000,000 views).

---
