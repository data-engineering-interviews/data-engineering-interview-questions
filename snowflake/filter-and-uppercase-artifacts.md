# Filter and Uppercase Artifacts

> **Company:** AMD | **Difficulty:** Easy

---

#### Scenario

You are helping an archaeological team manage their artifact inventory stored in a single table.

#### Task

Write a Snowflake SQL query that:
1. Selects all columns from `{{ ref("artifacts") }}`
2. Converts the `Material` column to uppercase using `UPPER`
3. Filters to only include rows where `Quantity` is strictly greater than 100
4. Returns columns: `ID`, `Item`, `Period`, `Material`, `Quantity`

#### Schema

**artifacts**

| Column | Type | Description |
|--------|------|-------------|
| ID | String | Unique identifier for the artifact |
| Item | String | Type of artifact (e.g. pottery, weapon, jewel) |
| Period | String | Archaeological period the item originates from |
| Material | String | Material the artifact is made from |
| Quantity | Integer | Number of items found |

#### Example

**artifacts:**

| ID | Item | Period | Material | Quantity |
|---|---|---|---|---|
| 1 | Vase | Prehistoric | ceramic | 160 |
| 2 | Dagger | Medieval | iron | 75 |
| 3 | Ring | Roman | silver | 210 |
| 4 | Bowl | Bronze Age | copper | 100 |
| 5 | Amulet | Iron Age | jade | 130 |

**Expected Output:**

| ID | Item | Period | Material | Quantity |
|---|---|---|---|---|
| 1 | Vase | Prehistoric | CERAMIC | 160 |
| 3 | Ring | Roman | SILVER | 210 |
| 5 | Amulet | Iron Age | JADE | 130 |

> **Note:** Row 2 is excluded (Quantity 75 is not greater than 100). Row 4 is excluded (Quantity 100 is not strictly greater than 100). Material values are converted to uppercase.

---
