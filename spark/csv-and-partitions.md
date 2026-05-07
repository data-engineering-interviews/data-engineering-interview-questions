# CSV and Partitions

> **Company:** Atlassian | **Difficulty:** Easy

---

#### Objective

When Spark reads a file, it splits the data into partitions (chunks that can be processed in parallel across the cluster). The number of partitions Spark creates depends on the file size and the value of `spark.sql.files.maxPartitionBytes` (default 128MB). Getting a feel for how Spark partitions your data is one of the first steps to understanding parallel execution.

#### Task

A file with 5,000 order records is available at `/home/interview/orders.csv`. A starter script has been created for you at `/home/interview/read_partitions.py` with a SparkSession and the CSV already loaded into a DataFrame called `df`. Complete the script to find the number of partitions and print it in the exact format: `number of partitions = <N>`

#### **Example**

```
number of partitions = 1
```

_Note: The actual value depends on file size and Spark's default configuration._

---
