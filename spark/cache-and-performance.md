# Cache and Performance

> **Company:** Palantir | **Difficulty:** Medium

---

#### Objective

Spark uses lazy evaluation, which means transformations are recomputed from scratch every time an action is triggered. If you plan to reuse a DataFrame multiple times, this can be wasteful. The `cache()` method tells Spark to store the DataFrame in memory after the first computation, so subsequent actions can read from memory instead of re-reading and re-parsing the source data. Caching is one of the most practical Spark optimizations, especially when iterating over the same dataset in machine learning pipelines or exploratory analysis.

#### Task

A dataset with 50,000 order records is available at `/home/interview/orders.csv`. A starter script has been created for you at `/home/interview/cache_performance.py` with a SparkSession and the CSV already loaded into a DataFrame called `df`. Cache the DataFrame, run `count()` twice while measuring each runtime, and print the results in the exact format:

```
first run = <time>s
second run = <time>s
faster after caching = true
```

#### **Example**

```
first run = 1.24s
second run = 0.05s
faster after caching = true
```

---
