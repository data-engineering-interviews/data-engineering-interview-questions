# Extract Schema Information from Parquet File Using PyArrow

> **Company:** Palantir | **Difficulty:** Easy

---

#### Scenario

A Parquet file contains structured data and you need to extract and document its schema information for analysis purposes.

#### Task

Write a Python script at `/home/interview/extract_schema.py` using pyarrow that reads `/home/interview/data.parquet`, extracts the schema information (column names, data types, compression codec, row count, and file size), and saves the output as JSON to `/home/interview/schema_info.json`.



#### Example

Expected output format in `/home/interview/schema_info.json`:
```json
{
  "file": "/home/interview/data.parquet",
  "row_count": 390,
  "file_size_bytes": 45632,
  "file_size_kb": 44.56,
  "compression_codec": "SNAPPY",
  "columns": [
    {
      "name": "id",
      "type": "int64"
    },
    {
      "name": "name",
      "type": "string"
    }
  ]
}
```

---
