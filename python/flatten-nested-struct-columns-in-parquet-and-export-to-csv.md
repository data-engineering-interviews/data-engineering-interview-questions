# Flatten Nested Struct Columns in Parquet and Export to CSV

> **Company:** Coinbase | **Difficulty:** Medium

---

#### Scenario

A Parquet file contains customer data with nested struct columns that need to be flattened for easier analysis and export to CSV format.

#### Task

Write a Python script at `/home/interview/flatten_data.py` using pandas that reads `/home/interview/customers_nested.parquet`, flattens all nested struct columns into separate columns with underscore naming (e.g., `address_street`, `contact_phone`), and writes the result to `/home/interview/flattened_data.csv`.



#### Example

Input (nested structure):
```
id | first_name | address                                 | contact
1  | John       | {street: "123 Main", city: "NYC", ...} | {phone: "555-0100", ...}
```

Expected output (flattened):
```
id | first_name | address_street | address_city | contact_phone | ...
1  | John       | 123 Main       | NYC          | 555-0100      | ...
```