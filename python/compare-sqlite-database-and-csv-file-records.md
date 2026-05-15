# Compare SQLite Database and CSV File Records

> **Company:** Robinhood | **Difficulty:** Easy

---

#### Scenario

A SQLite database and a CSV file both contain customer records, but they may be out of sync. You need to identify which records exist in one source but not the other.

#### Task

Write a Python script at `/home/interview/compare_data.py` that connects to the SQLite database at `/home/interview/customers.db`, reads the CSV file at `/home/interview/customers.csv`, compares the customer IDs in both sources, and saves a report to `/home/interview/comparison_report.json` showing which IDs are unique to each source.

#### Example

Expected output format in `/home/interview/comparison_report.json`:
```json
{
  "extra_in_sql": [103, 105, 108],
  "extra_in_csv": [15, 42, 87, 91]
}
```

Where `extra_in_sql` contains IDs present in the database but missing from the CSV, and `extra_in_csv` contains IDs present in the CSV but missing from the database.

---
