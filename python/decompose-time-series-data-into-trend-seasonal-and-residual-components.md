# Decompose Time-Series Data into Trend, Seasonal, and Residual Components

> **Company:** Instacart | **Difficulty:** Medium

---

#### Scenario

A CSV file contains daily temperature readings over multiple years. You need to decompose this time-series data to analyze its underlying patterns.

#### Task

Write a Python script at `/home/interview/decompose_timeseries.py` using statsmodels that reads `/home/interview/temperature_data.csv`, decomposes the temperature time-series into trend, seasonal, and residual components using additive decomposition, and saves each component to separate CSV files: `/home/interview/trend.csv`, `/home/interview/seasonal.csv`, and `/home/interview/residual.csv`.



#### Example

Input (`temperature_data.csv`):
```
date,temperature
2023-01-01,8.5
2023-01-02,9.2
...
```

Expected outputs:
- `trend.csv` - Long-term trend component
- `seasonal.csv` - Repeating seasonal pattern
- `residual.csv` - Random fluctuations

---
