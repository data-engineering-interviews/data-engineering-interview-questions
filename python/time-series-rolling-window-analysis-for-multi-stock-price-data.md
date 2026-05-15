# Time-Series Rolling Window Analysis for Multi-Stock Price Data

> **Company:** HashiCorp | **Difficulty:** Medium

---

#### Scenario

A CSV file contains daily stock price data for multiple companies that needs statistical analysis using rolling window calculations across different time periods.

#### Task

Write a Python script at `/home/interview/calculate_rolling.py` using pandas that reads `/home/interview/stock_data.csv`, calculates rolling statistics (mean, sum, standard deviation) for the `close_price` column using three different window sizes (7-day, 14-day, 30-day), rounds all calculated values to 2 decimal places, and saves the result to `/home/interview/rolling_stats.csv`.



#### Example

Input (`stock_data.csv`):
```
date,ticker,close_price
2025-01-01,AAPL,180.50
2025-01-01,GOOGL,142.30
2025-01-02,AAPL,182.10
2025-01-02,GOOGL,143.20
...
```

Expected output (`rolling_stats.csv`):
```
date,ticker,close_price,rolling_mean_7d,rolling_sum_7d,rolling_std_7d,rolling_mean_14d,...
2025-01-01,AAPL,180.50,,,,,...
...
2025-01-07,AAPL,185.20,182.45,1277.15,2.34,...
...
```

---
