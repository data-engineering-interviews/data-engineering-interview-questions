# Usage and Accuracy per Model Type

> **Company:** VMware | **Difficulty:** Medium

---

#### Scenario

You work as an AI engineer at a technology company and have been given two tables containing information about AI models and their daily usage records.

#### Task

Write a Snowflake SQL query that:
1. Joins `{{ ref("models") }}` with `{{ ref("usage_logs") }}` on `Model_ID`
2. Computes `Total_Uses` as the sum of `Uses` for each model
3. Computes `Average_Accuracy` as the average `Accuracy` across all models sharing the same `Model_Type`, rounded to 2 decimal places, using a window function
4. Returns the columns `Model_ID`, `Model_Name`, `Model_Type`, `Accuracy`, `Total_Uses`, and `Average_Accuracy`

#### Schema

**models**

| Column | Type | Description |
|--------|------|-------------|
| Model_ID | String | Unique identifier for each AI model |
| Model_Name | String | Display name of the model |
| Model_Type | String | Category of the model (e.g., Classification, NLP) |
| Accuracy | Float | Accuracy score of the model |

**usage_logs**

| Column | Type | Description |
|--------|------|-------------|
| Model_ID | String | Foreign key referencing the models table |
| Date | Date | Date of recorded usage |
| Uses | Integer | Number of times the model was used on that date |

#### Example

**models:**

| Model_ID | Model_Name | Model_Type | Accuracy |
|---|---|---|---|
| A1 | AlphaNet | Classification | 0.91 |
| A2 | BetaVision | Classification | 0.87 |
| A3 | GammaText | NLP | 0.82 |
| A4 | DeltaGen | Generative | 0.76 |
| A5 | EpsilonNLP | NLP | 0.90 |

**usage_logs:**

| Model_ID | Date | Uses |
|---|---|---|
| A1 | 2024-03-01 | 80 |
| A1 | 2024-03-02 | 60 |
| A2 | 2024-03-01 | 150 |
| A3 | 2024-03-01 | 200 |
| A3 | 2024-03-03 | 90 |
| A4 | 2024-03-02 | 110 |
| A5 | 2024-03-01 | 75 |

**Expected Output:**

| Model_ID | Model_Name | Model_Type | Accuracy | Total_Uses | Average_Accuracy |
|---|---|---|---|---|---|
| A1 | AlphaNet | Classification | 0.91 | 140 | 0.89 |
| A2 | BetaVision | Classification | 0.87 | 150 | 0.89 |
| A3 | GammaText | NLP | 0.82 | 290 | 0.86 |
| A4 | DeltaGen | Generative | 0.76 | 110 | 0.76 |
| A5 | EpsilonNLP | NLP | 0.90 | 75 | 0.86 |

> **Note:** `Total_Uses` sums all usage rows per model (e.g., A1 has 80 + 60 = 140). `Average_Accuracy` averages the accuracy of all models in the same type (e.g., Classification models A1 and A2 share (0.91 + 0.87) / 2 = 0.89).

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/usage-and-accuracy-per-model-type)
