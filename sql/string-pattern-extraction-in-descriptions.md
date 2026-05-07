# String Pattern Extraction in Descriptions

> **Company:** Zscaler | **Difficulty:** Medium

---

#### Objective
Given a table named `products` with the columns `product_id`, `name`, `description`, and `price`, write an SQL query to retrieve the `product_id`, `name`, and the first email address found within the `description` for each product. Only include products that have an email address in their `description`. The resulting list should be ordered by `product_id` in ascending order.

#### Additional information
- An email address is defined by the pattern `word@word.word`.
- The extracted email should be the first occurrence found in the `description`.
- Products without an email address in the `description` should not appear in the result.
- Ensure the output columns are named exactly as `product_id`, `name`, and `email_found`.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/string-pattern-extraction-in-descriptions)
