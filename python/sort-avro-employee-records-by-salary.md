# Sort Avro Employee Records by Salary

> **Company:** GitHub | **Difficulty:** Easy

---

#### Scenario

An Avro file contains employee records that need to be analyzed. The data must be sorted to identify salary distribution across the organization.

#### Task

Write a Python script at `/home/interview/sort_employees.py` that reads `/home/interview/employees.avro`, sorts all records by salary in descending order (highest to lowest), and saves the sorted data as JSON to `/home/interview/sorted_employees.json`.



#### Example

Expected output format in `/home/interview/sorted_employees.json`:
```json
[
  {
    "id": 45,
    "name": "John Smith",
    "department": "Engineering",
    "salary": 150000,
    "hire_date": "2020-03-15",
    "is_active": true
  },
  {
    "id": 89,
    "name": "Jane Doe",
    "department": "Sales",
    "salary": 145000,
    "hire_date": "2019-07-22",
    "is_active": true
  }
]
```