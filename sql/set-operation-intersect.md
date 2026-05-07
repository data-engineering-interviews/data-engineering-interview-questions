# Set Operation: INTERSECT

> **Company:** DoorDash | **Difficulty:** Medium

---

#### Objective
Retrieve the list of customers who meet both of the following criteria:
1. They are new customers with a monthly spending greater than 1000.
2. They are loyal customers with at least 3 years of membership and have a 'Premium' tier status.

Provide the `customer_id` and `name` of these customers, sorted in ascending order by `customer_id`.

#### Additional information
- **Tables Description**:

  The `NewCustomers` table:

  | Column | Type | Description |
  |--------|------|-------------|
  | customer_id | INTEGER | Unique identifier for each customer |
  | name | VARCHAR | Name of the customer |
  | monthly_spend | INTEGER | Amount spent by the customer monthly |
  | join_date | DATE | Date when the customer joined |

  The `LoyalCustomers` table:

  | Column | Type | Description |
  |--------|------|-------------|
  | customer_id | INTEGER | Unique identifier for each customer |
  | name | VARCHAR | Name of the customer |
  | membership_years | INTEGER | Number of years the customer has been a member |
  | tier | VARCHAR | Membership tier of the customer (e.g., 'Premium') |

- **Constraints**:
  - Each customer appears only once in each table.
  - `membership_years` and `monthly_spend` are positive integers.
  - The `tier` field contains single-word strings without special characters.

- **Output Requirements**:
  - The result should include only the `customer_id` and `name` columns.
  - The final output must be ordered by `customer_id` in ascending order.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/set-operation-intersect)
