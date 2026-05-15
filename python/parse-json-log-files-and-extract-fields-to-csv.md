# Parse JSON Log Files and Extract Fields to CSV

> **Company:** Okta | **Difficulty:** Easy

---

#### Scenario

A log file contains JSON-formatted application logs with one JSON object per line. The logs have inconsistent structure - some fields may be missing, and some logs contain nested context information that needs to be extracted.

#### Task

Write a Python script at `/home/interview/parse_logs.py` that reads `/home/interview/app.log`, parses each JSON line, extracts the `timestamp`, `level`, `user_id`, `message`, and `request_id` (from nested context) fields, and saves them to `/home/interview/logs_table.csv`. Use empty strings for missing fields.

#### Example

Input log lines:
```json
{"timestamp": "2026-02-11T10:30:45", "level": "INFO", "user_id": "user_123", "message": "User logged in", "context": {"request_id": "req_456", "endpoint": "/api/auth"}}
{"timestamp": "2026-02-11T10:31:15", "level": "ERROR", "message": "Database connection failed"}
```

Expected CSV output:
```
timestamp,level,user_id,message,request_id
2026-02-11T10:30:45,INFO,user_123,User logged in,req_456
2026-02-11T10:31:15,ERROR,,Database connection failed,
```

---
