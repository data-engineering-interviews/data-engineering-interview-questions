# Assign Row Numbers to Authors per Paper

> **Company:** Cloudflare | **Difficulty:** Medium

---

#### Scenario

You work for an AI research organization that tracks research papers and their contributing authors.

#### Task

Write a Snowflake SQL query that:
1. Joins `{{ ref("authors") }}` with `{{ ref("research_papers") }}` on `paper_id`
2. Assigns a sequential `row_number` to each author, partitioned by `paper_id` and ordered by `author_id`
3. Returns the columns: `paper_id`, `author_id`, `name`, `row_number`

#### Schema

**research_papers**

| Column | Type | Description |
|--------|------|-------------|
| paper_id | String | Unique identifier for the paper |
| title | String | Title of the research paper |
| year | Integer | Year the paper was published |

**authors**

| Column | Type | Description |
|--------|------|-------------|
| paper_id | String | Paper this author contributed to |
| author_id | String | Unique identifier for the author |
| name | String | Full name of the author |

#### Example

**research_papers:**

| paper_id | title | year |
|----------|-------|------|
| P1 | Scalable Data Pipelines | 2021 |
| P2 | Edge Computing Strategies | 2023 |
| P3 | Privacy in Distributed Systems | 2022 |

**authors:**

| paper_id | author_id | name |
|----------|-----------|------|
| P1 | A1 | Nora Chen |
| P1 | A2 | Leo Park |
| P2 | A3 | Diana Ruiz |
| P2 | A4 | Marcus Holt |
| P2 | A5 | Priya Nair |
| P3 | A6 | Sam Ortega |
| P3 | A7 | Tina Farah |

**Expected Output:**

| paper_id | author_id | name | row_number |
|----------|-----------|------|------------|
| P1 | A1 | Nora Chen | 1 |
| P1 | A2 | Leo Park | 2 |
| P2 | A3 | Diana Ruiz | 1 |
| P2 | A4 | Marcus Holt | 2 |
| P2 | A5 | Priya Nair | 3 |
| P3 | A6 | Sam Ortega | 1 |
| P3 | A7 | Tina Farah | 2 |

> **Note:** The `row_number` resets to 1 for each new `paper_id`. Within a paper, authors are numbered in ascending order by `author_id`.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/assign-row-numbers-to-authors-per-paper)
