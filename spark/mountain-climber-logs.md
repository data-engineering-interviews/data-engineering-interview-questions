# Mountain Climber Logs

> **Company:** Stripe | **Difficulty:** Hard

---

#### Objective

You are analyzing expedition logs. You have two DataFrames: `mountain_info`, containing details about various peaks, and `mountain_climbers`, which logs individual ascents.

#### Task

Write a PySpark script to find the most recent climber for each mountain. Your output should only contain mountains that have been climbed by at least one person.

The final DataFrame must be saved as `result_df` and include the mountain's name, the last climber's name, and the date and time of that most recent climb. Rename the output columns to match the expected schema below.

#### File Path

* Mountain Info Dataset: `/home/interview/mountain_info.csv`
* Mountain Climbers Dataset: `/home/interview/mountain_climbers.csv`
* Starter script: `/home/interview/latest_climbers.py`

#### Schema

**mountain_info.csv**

| Column Name | Data Type |
| --- | --- |
| name        | string    |
| height      | integer    |
| country      | string    |
| range        | string    |

**mountain_climbers.csv**

| Column Name    | Data Type |
| --- | --- |
| climber_name  | string    |
| mountain_name | string    |
| climb_date    | date      |
| climb_time    | double    |

**Expected Output Schema**

| Column Name        | Data Type |
| --- | --- |
| mountain_name      | string    |
| last_climber_name | string    |
| last_climb_date    | date      |
| last_climb_time    | double    |

#### **Example**

Given this sample input:

**mountain_info**

| name              | height | country  | range        |
| --- | --- | --- | --- |
| Mount Everest      | 8848    | Nepal    | Himalayas    |
| Mount Kilimanjaro | 5895    | Tanzania | Kilimanjaro |
| Mount Denali      | 6190    | USA      | Alaska      |
| Mount Fuji        | 3776    | Japan    | Fuji        |
| Mont Blanc        | 4808    | France    | Alps        |

**mountain_climbers**

| climber_name | mountain_name      | climb_date | climb_time |
| --- | --- | --- | --- |
| John          | Mount Everest      | 2020-01-01 | 8.5        |
| Jane          | Mount Everest      | 2022-02-02 | 9.0        |
| Jim          | Mount Kilimanjaro | 2021-03-03 | 6.0        |
| Jess          | Mount Kilimanjaro | 2022-04-04 | 7.0        |
| Joe          | Mount Denali      | 2022-05-05 | 10.0        |
| Jill          | Mount Denali      | 2021-06-06 | 11.0        |

The output would be:

| mountain_name      | last_climber_name | last_climb_date | last_climb_time |
| --- | --- | --- | --- |
| Mount Everest      | Jane              | 2022-02-02      | 9.0              |
| Mount Kilimanjaro | Jess              | 2022-04-04      | 7.0              |
| Mount Denali      | Joe                | 2022-05-05      | 10.0            |

Notice how Mount Fuji and Mont Blanc are excluded because they do not appear in the climbers log in this specific excerpt. For Everest, Jane's 2022 climb is kept over John's 2020 climb.

---
