# Merge Multiple Address Fields

> **Company:** Datadog | **Difficulty:** Easy

---

#### Objective
Write an SQL query to retrieve each customer's ID, first name, last name, and a consolidated full address. The full address should seamlessly combine the street address, city, state, and postal code, properly handling cases where some address components may be missing. Ensure that the results are sorted by the customer ID in ascending order.

#### Additional information
- If an address component (street address, city, state, or postal code) is `NULL`, it should be excluded from the `full_address`.
- Use commas and spaces to separate the available address components appropriately.
  - Insert a comma and space after the street address if city, state, or postal code is present.
  - Insert a comma and space after the city if state or postal code is present.
  - Insert a space between the state and postal code if both are present.
- If all address components are missing, the `full_address` should be an empty string.
- The final output should include the columns: `customer_id`, `first_name`, `last_name`, and `full_address`.
- Order the resulting records by `customer_id` in ascending order.

---
📹 [Video Solution](https://prepare.sh/interview/data-engineering/code/merge-multiple-address-fields)
