# Amusement Park Rating Anomalies

> **Company:** GitHub | **Difficulty:** Medium

---

#### Scenario

You are a Data Analyst at an amusement park and need to identify rides whose average visitor rating deviates significantly from the norm.

#### Task

Write a Snowflake SQL query that:
1. Joins `{{ ref("rides") }}` with `{{ ref("visitors") }}` on `ride_id` using an inner join (rides with no visitor ratings should be excluded)
2. Computes the average rating per ride (rounded to 2 decimal places)
3. Computes the global mean and standard deviation of all rides' average ratings using window functions
4. Flags each ride as anomalous when its average rating deviates from the global mean by more than one standard deviation
5. Returns `ride_id`, `ride_name`, `average_rating`, and `is_anomalous`

#### Schema

**rides**

| Column | Type | Description |
|--------|------|-------------|
| ride_id | String | Unique identifier for the ride |
| ride_name | String | Name of the ride |
| type | String | Category of the ride |
| capacity | Integer | Maximum number of riders per cycle |

**visitors**

| Column | Type | Description |
|--------|------|-------------|
| visitor_id | String | Unique identifier for the visitor |
| ride_id | String | Ride the visitor went on |
| visit_date | Date | Date of the visit |
| rating | Integer | Rating given by the visitor (1 to 5) |

#### Example

**rides:**

| ride_id | ride_name | type | capacity |
|---|---|---|---|
| R001 | Thunder Canyon | Thrill | 28 |
| R002 | Sky Glider | Observation | 50 |
| R003 | Splash Falls | Water | 18 |
| R004 | Turbo Karts | Family | 22 |
| R005 | Gentle River | Classic | 36 |

**visitors:**

| visitor_id | ride_id | visit_date | rating |
|---|---|---|---|
| V01 | R001 | 2024-06-10 | 5 |
| V02 | R001 | 2024-06-10 | 4 |
| V01 | R002 | 2024-06-10 | 3 |
| V03 | R003 | 2024-06-11 | 1 |
| V04 | R004 | 2024-06-11 | 5 |
| V02 | R004 | 2024-06-11 | 5 |

**Expected Output:**

| ride_id | ride_name | average_rating | is_anomalous |
|---|---|---|---|
| R001 | Thunder Canyon | 4.5 | false |
| R002 | Sky Glider | 3.0 | false |
| R003 | Splash Falls | 1.0 | true |
| R004 | Turbo Karts | 5.0 | false |

> **Note:** R005 (Gentle River) has no visitor ratings and is excluded. R003 (Splash Falls) has an average rating of 1.0, which deviates from the global mean (3.375) by more than one standard deviation (1.797), so it is flagged as anomalous.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/amusement-park-rating-anomalies)
