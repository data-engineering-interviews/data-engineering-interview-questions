# Repartition

> **Company:** Robinhood | **Difficulty:** Easy

---

#### Objective

When Spark reads a small file, it often creates just 1 partition, which means only 1 task processes the entire dataset. In production, you'll frequently want more partitions so Spark can process data in parallel across multiple cores. The `repartition()` method lets you control this by redistributing data across a specified number of partitions, where each partition maps to exactly one parallel task.

#### Task

An orders dataset with 5,000 records is available at `/home/interview/orders.csv`. A starter script has been created for you at `/home/interview/repartition_tasks.py` with a SparkSession and the CSV already loaded into a DataFrame called `df`. Repartition the DataFrame to `8` partitions and print the resulting task count in the exact format: `task count = 8`

#### **Example**

```
task count = 8
```

---
