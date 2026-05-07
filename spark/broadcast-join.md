# Broadcast Join

> **Company:** Databricks | **Difficulty:** Easy

---

#### Objective

When joining two DataFrames, Spark normally shuffles both tables across the network so matching keys end up on the same executor. If one of the tables is small enough, Spark can instead **broadcast** it (send a full copy to every executor), so each executor can join locally without any shuffle. This is called a broadcast join and it's one of the most common Spark optimizations for joining a large fact table with a small dimension table.

#### Task

Two datasets are available: a large orders file (`/home/interview/orders.csv` with 5,000 records) and a small customers file (`/home/interview/customers.csv` with 50 records). 

A starter script has been created for you at `/home/interview/broadcast_join.py` with a SparkSession and both CSVs already loaded as `orders_df` and `customers_df`. 

Join the two DataFrames on `customer_id` using a broadcast join on the smaller table, count the number of orders per city, and print the number of distinct cities in the exact format: 

`cities with orders = <N>`

#### **Example**

```
cities with orders = 42
```

---
