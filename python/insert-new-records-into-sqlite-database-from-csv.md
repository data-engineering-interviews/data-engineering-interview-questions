# Insert New Records into SQLite Database from CSV

> **Company:** Visa | **Difficulty:** Medium

---

#### Scenario

A CSV file contains customer records that need to be imported into a database. Some records may already exist in the database and should not be duplicated.

#### Task

Write a Python script at `/home/interview/insert_new_records.py` that reads `/home/interview/new_customers.csv`, checks if each record already exists in the `customers` table of `/home/interview/customers.db` (based on the `id` field), and inserts only the new records.