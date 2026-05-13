# Export SQLite Database to Parquet Format with Metadata

> **Company:** GitLab | **Difficulty:** Hard

---

#### Scenario

An SQLite database contains e-commerce data that needs to be exported to Parquet format for analytics processing. The export must preserve table relationships and provide metadata about the conversion.

#### Task

Write a Python script at `/home/interview/export_to_parquet.py` that connects to `/home/interview/ecommerce.db`, extracts all tables, converts each to Parquet format with Snappy compression, and creates a manifest file. Save outputs to `/home/interview/parquet_export/` directory.


#### Database Schema

| Table | Columns | Foreign Keys |
|-------|---------|--------------|
| **customers** | id, name, email, created_at | - |
| **products** | id, name, price, category, stock | - |
| **orders** | id, customer_id, product_id, order_date, total_amount, status | customer_id → customers.id, product_id → products.id |

#### Manifest Requirements

Create `manifest.json` containing: export timestamp, compression type, and for each table: table name, file name, row count, file size, and foreign key relationships.

#### Example Manifest
```json
{
  "export_timestamp": "2026-02-13T10:30:00",
  "compression": "snappy",
  "tables": [
    {
      "table_name": "orders",
      "file_name": "orders.parquet",
      "row_count": 200,
      "file_size_bytes": 23456,
      "foreign_keys": [
        {"column": "customer_id", "references_table": "customers", "references_column": "id"}
      ]
    }
  ]
}
```