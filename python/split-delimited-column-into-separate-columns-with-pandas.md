# Split Delimited Column into Separate Columns with Pandas

> **Company:** Snowflake | **Difficulty:** Easy

---

#### Scenario

A CSV file contains a column with comma-delimited data that needs to be split into separate columns for easier analysis.

#### Task

Write a Python script at `/home/interview/split_columns.py` using pandas that reads `/home/interview/data.csv`, splits the `full_info` column into separate columns (`first_name`, `last_name`, `age`), and saves the result to `/home/interview/split_data.csv`.



#### Example

Input (`data.csv`):
```
id,full_info
1,"John,Doe,30"
2,"Jane,Smith,25"
```

Expected output (`split_data.csv`):
```
id,first_name,last_name,age
1,John,Doe,30
2,Jane,Smith,25
```