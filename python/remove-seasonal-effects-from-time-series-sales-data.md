# Remove Seasonal Effects from Time-Series Sales Data

> **Company:** Cloudflare | **Difficulty:** Hard

---

#### Scenario

A company's monthly sales data shows recurring seasonal patterns that need to be removed to analyze the underlying trend and make better forecasts.

#### Task

Write a Python script at `/home/interview/remove_seasonality.py` that reads `/home/interview/sales_data.csv` containing monthly sales data with 12-month seasonality, removes the seasonal effects using seasonal decomposition with an additive model, and saves the deseasonalized values (rounded to 2 decimal places) to `/home/interview/deseasonalized_sales.csv`.

The deseasonalized values should be calculated as the original sales with the seasonal component removed (trend + residual). Ensure all rows from the input are preserved in the output by handling edge effects appropriately.


#### Example

Input (`sales_data.csv`):
```
date,sales
2023-01-01,45000.00
2023-02-01,48000.00
2023-03-01,52000.00
...
```

Expected output (`deseasonalized_sales.csv`):
```
date,deseasonalized_sales
2023-01-01,50123.45
2023-02-01,50234.67
2023-03-01,50345.89
...
```

---
