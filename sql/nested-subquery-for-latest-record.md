# Nested Subquery for Latest Record

> **Company:** DoorDash | **Difficulty:** Medium

---

#### Objective
Given a table named `events` with the following columns:

| Column | Type | Description |
|--------|------|-------------|
| id | INTEGER | The unique identifier for each event |
| event_name | VARCHAR | The name of the event |
| user_id | INTEGER | The identifier of the user associated with the event |
| event_date | DATE | The date when the event occurred |
| status | VARCHAR | The status of the event |

Write an SQL query to fetch the most recent event for each user. The result should include the `event_name`, `user_id`, `event_date`, and `status` of these latest events, sorted in ascending order by `user_id`.

#### Additional information
- Each user may have multiple events recorded in the `events` table.
- The `event_date` for each event is unique per user.
- If a user has multiple events on the same latest date, you can return any one of them.
- Ensure that your query is optimized for performance, especially with large datasets.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/nested-subquery-for-latest-record)
