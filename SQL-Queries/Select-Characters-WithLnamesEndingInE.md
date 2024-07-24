# Select Characters with Last Names Ending in 'e'

**Description:**
This query retrieves the last names of characters where the last name ends with the letter 'e'.

**SQL Query:**

```sql
SELECT lname
FROM characters
WHERE lname LIKE '%e';

```

| lname    |
|----------|
| Blake    |
| Greene   |
| Moore    |
| ...      |

