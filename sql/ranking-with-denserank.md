# Ranking with Dense_Rank

> **Company:** Amazon | **Difficulty:** Medium

---

#### Objective
Given a table named `sales` that records individual sales made by sales representatives, write a SQL query to compute the total sales for each salesperson. Assign a rank to each salesperson based on their total sales in descending order using dense ranking, ensuring that salespeople with identical total sales receive the same rank without gaps in the ranking sequence. The final output should list the salesperson's name, their total sales, and their sales rank, ordered first by rank and then alphabetically by name.

#### Additional information
- **Table Schema**:

    The `sales` table:

    | Column | Type | Description |
    |--------|------|-------------|
    | salesperson_id | INTEGER | Unique identifier for each salesperson |
    | salesperson_name | VARCHAR | Name of the salesperson |
    | sale_amount | INTEGER | Amount of an individual sale |

- **Constraints**:
    - The `sales` table contains at least one record.
    - Total sales for each salesperson are calculated as the sum of their `sale_amount` values.
    - Utilize SQL window functions to determine the sales rankings.

- **Output Requirements**:
    - Columns to return:

| Column | Description |
|--------|-------------|
| salesperson_name | Name of the salesperson |
| total_sales | Sum of all sales amounts for the salesperson |
| sales_rank | Dense rank based on `total_sales` in descending order |

    - Order the results first by `sales_rank` in ascending order, then by `salesperson_name` in ascending order.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/ranking-with-denserank)
