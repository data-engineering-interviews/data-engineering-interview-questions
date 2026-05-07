# Window Function for Moving Average

> **Company:** DeutscheBank | **Difficulty:** Medium

---

#### Objective
Given a table `sales` with columns `sale_date` (in `YYYY-MM-DD` format) and `amount`, write an SQL query to compute the 7-day moving average of `amount` for each `sale_date`. The moving average should include the current day and the six preceding days. Round the moving average to two decimal places.

#### Additional information
- The output should include the columns `sale_date`, `amount`, and `moving_average`.
- Order the results by `sale_date` in ascending order.
- Utilize appropriate SQL window functions to efficiently calculate the moving average.
- Assume that there are no duplicate `sale_date` entries and that `sale_date` values are consecutive without gaps.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/window-function-for-moving-average)
