# Aggregate Time-Series Data into Fixed Time Windows

> **Company:** Tesla | **Difficulty:** Hard

---

#### Scenario

A sensor generates temperature and humidity readings at irregular intervals. The data needs to be aggregated into fixed 15-minute time windows for analysis.

#### Task

Write a Python script at `/home/interview/aggregate_timeseries.py` that reads `/home/interview/sensor_data.csv`, aggregates the data into 15-minute windows calculating mean, min, and max values for both temperature and humidity, and writes the result to `/home/interview/aggregated_data.csv`.

Round all numeric values to 2 decimal places.


#### Example

Expected output format in `/home/interview/aggregated_data.csv`:
```
window_start,window_end,temp_mean,temp_min,temp_max,humidity_mean,humidity_min,humidity_max
2026-02-13 10:00:00,2026-02-13 10:15:00,22.5,21.2,23.8,45.3,43.1,47.5
2026-02-13 10:15:00,2026-02-13 10:30:00,23.1,22.0,24.2,46.8,44.2,49.1
...
```