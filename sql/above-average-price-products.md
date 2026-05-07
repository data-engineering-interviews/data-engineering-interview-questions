# Above Average Price Products

> **Company:** Hulu | **Difficulty:** Medium

---

#### Objective
Construct an SQL query to fetch all products that are currently available in stock and priced above the average price of all available products. The resulting list should be sorted primarily by price in descending order and secondarily by rating in descending order, ensuring that products without a rating appear at the end.

#### Additional information
- Only include products where `stock_quantity` is greater than 0.
- The average price should be calculated based only on products that are in stock.
- When sorting, products with a `NULL` rating should be listed after those with non-null ratings.
- The query should return all columns from the `Products` table.
- Handle scenarios where some products might not have a rating value.

```sql
Products  
--------  
product_id INT  
name VARCHAR  
price DECIMAL(10,2)  
stock_quantity INT  
rating DECIMAL(3,2) NULL
```

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/above-average-price-products)
