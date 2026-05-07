# Filter Movies with Missing Box Office Data

> **Company:** DoorDash | **Difficulty:** Easy

---

#### Scenario

You work at a movie analytics company and have been given a table of movies released in 2023.

#### Task

Write a Snowflake SQL query that:
1. Selects all columns from `{{ ref("movies") }}`
2. Filters to return only rows where `box_office_collection` is NULL

#### Schema

**movies**

| Column | Type | Description |
|--------|------|-------------|
| movie_id | Integer | Unique identifier for the movie |
| movie_title | String | Title of the movie |
| director_name | String | Name of the director |
| release_date | Date | Release date of the movie |
| box_office_collection | Float | Box office earnings (NULL if not recorded) |
| genre | String | Genre of the movie |

#### Example

**movies:**

| movie_id | movie_title | director_name | release_date | box_office_collection | genre |
|---|---|---|---|---|---|
| 1 | Coastal Drift | Ava Chen | 2023-03-15 | 542.30 | Drama |
| 2 | Neon Pulse | Marco Silva | 2023-06-22 | NULL | Action, Thriller |
| 3 | The Last Garden | Priya Rao | 2023-01-10 | 1287.45 | Drama, Romance |
| 4 | Orbit Zero | Jake Morrison | 2023-09-05 | NULL | Sci-Fi, Adventure |
| 5 | Bright Corners | Lena Okafor | 2023-04-18 | 310.75 | Comedy |
| 6 | Ironwood | Sam Reiter | 2023-11-30 | 2150.00 | Action, Adventure |

**Expected Output:**

| movie_id | movie_title | director_name | release_date | box_office_collection | genre |
|---|---|---|---|---|---|
| 2 | Neon Pulse | Marco Silva | 2023-06-22 | NULL | Action, Thriller |
| 4 | Orbit Zero | Jake Morrison | 2023-09-05 | NULL | Sci-Fi, Adventure |

> **Note:** Only rows where `box_office_collection` is NULL are returned. Rows with any numeric value (including 0) are excluded.

---
