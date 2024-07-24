# Calculate Average Age of All Characters

**Description:**
This query calculates the average age of all characters in the characters table, rounding the result to two decimal places.

**SQL Query:**

```sql
SELECT ROUND(AVG(age), 2) 
FROM characters;
  ```

**Result Example**

| ROUND(AVG(age), 2)|
|-------------------|
|       32.45       |



