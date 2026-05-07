# Most Common Order Status

> **Company:** Airbnb | **Difficulty:** Easy

---

#### Objective

One of the most common operations in Spark is aggregating data by a key and finding the top result. This involves a `groupBy` followed by a sort, both of which are **wide transformations** that trigger shuffles (Spark redistributes data across partitions so rows with the same key end up together). Understanding how to chain these operations efficiently is fundamental to writing performant Spark jobs.

#### Task

An orders dataset with 5,000 records is available at `/home/interview/orders.csv`. A starter script has been created for you at `/home/interview/shuffle_metrics.py` with a SparkSession and the CSV already loaded into a DataFrame called `df`. 

Find the order status with the highest count and print the result in the exact format: `most common status = <status>, count = <N>`

#### **Example**

```
most common status = completed, count = 969
```

---
