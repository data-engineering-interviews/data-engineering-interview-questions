# Filter Funded Startups

> **Company:** Salesforce | **Difficulty:** Easy

---

#### Scenario

You work with data about venture capital investors and the startups they fund. Each investor has a personal funding limit, and you need to find investors whose average funding across their startups strictly exceeds that limit.

#### Task

Write a Snowflake SQL query that:
1. Joins `{{ ref("investors") }}` with `{{ ref("startups") }}` on `investor_id`
2. Computes `avg_funding` as the average of `funding` grouped by investor (rounded to 2 decimal places)
3. Filters to only include investors where `avg_funding` is strictly greater than `funding_limit`
4. Returns `investor_id`, `investor_name`, and `avg_funding`

#### Schema

**investors**

| Column | Type | Description |
|--------|------|-------------|
| investor_id | String | Unique identifier for the investor |
| investor_name | String | Name of the investment firm |
| funding_limit | Float | Maximum acceptable average funding threshold |

**startups**

| Column | Type | Description |
|--------|------|-------------|
| startup_id | String | Unique identifier for the startup |
| startup_name | String | Name of the startup |
| investor_id | String | Identifier of the investor who funded this startup |
| funding | Float | Amount funded to this startup (in millions) |

#### Example

**investors:**

| investor_id | investor_name | funding_limit |
|---|---|---|
| INV1 | Horizon Capital | 3.0 |
| INV2 | Summit Partners | 2.5 |
| INV3 | Blue Ridge Fund | 4.0 |
| INV4 | Atlas Ventures | 1.8 |

**startups:**

| startup_id | startup_name | investor_id | funding |
|---|---|---|---|
| ST1 | DataPulse | INV1 | 3.5 |
| ST2 | CloudSync | INV1 | 2.5 |
| ST3 | NeuralEdge | INV2 | 4.0 |
| ST4 | PayLane | INV2 | 3.0 |
| ST5 | GreenGrid | INV3 | 4.0 |
| ST6 | HealthIO | INV3 | 4.0 |
| ST7 | CyberLock | INV4 | 2.5 |
| ST8 | SwiftShip | INV4 | 1.5 |

**Expected Output:**

| investor_id | investor_name | avg_funding |
|---|---|---|
| INV2 | Summit Partners | 3.5 |
| INV4 | Atlas Ventures | 2.0 |

> **Note:** INV1 is excluded (avg 3.0 equals limit 3.0), INV3 is excluded (avg 4.0 equals limit 4.0). The filter requires strictly greater than, so equal values do not qualify.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/filter-funded-startups)
