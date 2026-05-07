# Year-over-Year Revenue Growth

> **Company:** OpenAI | **Difficulty:** Easy

---

#### Objective
Write an SQL query that calculates the yearly revenue, the previous year's revenue, and the percentage growth in revenue year-over-year for a given set of financial transactions. The results should be rounded to two decimal places.

#### Additional information
- The `financials` table contains the columns `transaction_date` (DATE) and `amount` (NUMERIC).
- The `growth_percentage` is calculated as `((current year's revenue - previous year's revenue) / previous year's revenue) * 100`.
- If there is no previous year's revenue for a given year, the `previous_revenue` and `growth_percentage` should be `NULL`.
- Order the results by year in ascending order.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/year-over-year-revenue-growth)
