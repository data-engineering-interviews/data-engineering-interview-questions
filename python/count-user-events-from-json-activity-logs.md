# Count User Events from JSON Activity Logs

> **Company:** Uber | **Difficulty:** Easy

---

#### Scenario

A JSON file contains user activity logs with various events. You need to analyze the logs and generate a report showing how many events each user performed.

#### Task

Write a Python script at `/home/interview/count_events.py` that reads `/home/interview/activity_logs.json`, counts the number of events per user, and saves the results as a JSON file to `/home/interview/user_event_counts.json`.

#### Example

Expected output format in `/home/interview/user_event_counts.json`:
```json
{
  "user_123": 5,
  "user_456": 12,
  "user_789": 3
}
```