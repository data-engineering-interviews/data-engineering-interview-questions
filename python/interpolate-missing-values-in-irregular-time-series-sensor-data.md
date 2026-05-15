# Interpolate Missing Values in Irregular Time-Series Sensor Data

> **Company:** VMware | **Difficulty:** Hard

---

#### Scenario

An IoT sensor monitoring system has collected temperature and humidity data, but some readings are missing due to network issues or sensor failures. The data needs to be cleaned by interpolating the missing values.

#### Task

Write a Python script at `/home/interview/interpolate_data.py` using pandas that reads `/home/interview/sensor_data.csv`, interpolates missing values in the `temperature` and `humidity` columns using time-based interpolation, and saves the result to `/home/interview/interpolated_data.csv`. Round the interpolated values to 1 decimal place.



#### Data Structure

- `timestamp`: DateTime of the reading
- `sensor_id`: Sensor identifier (no missing values)
- `temperature`: Temperature in Celsius (contains missing values)
- `humidity`: Humidity percentage (contains missing values)

#### Example

Input with missing values:
```
timestamp,sensor_id,temperature,humidity
2026-02-13 10:00:00,S001,22.5,65.0
2026-02-13 10:07:30,S001,,
2026-02-13 10:15:45,S001,23.1,67.5
```

Expected output with interpolated values:
```
timestamp,sensor_id,temperature,humidity
2026-02-13 10:00:00,S001,22.5,65.0
2026-02-13 10:07:30,S001,22.8,66.2
2026-02-13 10:15:45,S001,23.1,67.5
```

---
