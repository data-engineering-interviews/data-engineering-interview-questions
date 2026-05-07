# Find the Last Climber per Mountain

> **Company:** Bloomberg | **Difficulty:** Medium

---

#### Scenario

You work with a mountain climbing registry that tracks which climbers have summited each mountain and when.

#### Task

Write a Snowflake SQL query that:
1. Joins `{{ ref("climbers") }}` with `{{ ref("mountains") }}` on the mountain name
2. For each mountain, finds the climber with the most recent `climb_date`
3. Returns `mountain_name`, the climber's name as `last_climber_name`, the date as `last_climb_date`, and the time as `last_climb_time`
4. Excludes any mountains that have no climbing records

#### Schema

**mountains**

| Column | Type | Description |
|--------|------|-------------|
| name | String | Name of the mountain |
| height | Integer | Height in meters |
| country | String | Country where the mountain is located |
| range | String | Mountain range it belongs to |

**climbers**

| Column | Type | Description |
|--------|------|-------------|
| climber_name | String | Name of the climber |
| mountain_name | String | Name of the mountain climbed |
| climb_date | Date | Date of the climb |
| climb_time | Double | Duration of the climb in hours |

#### Example

**mountains:**

| name | height | country | range |
|------|--------|---------|-------|
| Mount Rainier | 4392 | USA | Cascades |
| Matterhorn | 4478 | Switzerland | Alps |
| Mount Olympus | 2917 | Greece | Olympus |

**climbers:**

| climber_name | mountain_name | climb_date | climb_time |
|--------------|---------------|------------|------------|
| Alice | Mount Rainier | 2021-06-10 | 7.5 |
| Bob | Mount Rainier | 2023-08-15 | 6.0 |
| Carol | Matterhorn | 2022-07-20 | 11.0 |
| Dave | Matterhorn | 2024-01-05 | 9.5 |

**Expected Output:**

| mountain_name | last_climber_name | last_climb_date | last_climb_time |
|---------------|-------------------|-----------------|-----------------|
| Mount Rainier | Bob | 2023-08-15 | 6.0 |
| Matterhorn | Dave | 2024-01-05 | 9.5 |

> **Note:** Mount Olympus has no climbing records, so it does not appear in the output. For each mountain with climbers, only the row with the most recent `climb_date` is returned.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/find-the-last-climber-per-mountain)
