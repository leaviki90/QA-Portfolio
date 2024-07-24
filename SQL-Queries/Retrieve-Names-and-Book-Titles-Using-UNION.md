# Retrieve Names and Book Titles Using UNION

**Description:**
This query retrieves all names from the characters table and all book titles from the library table using the UNION operator. This operation combines the results from both tables, ensuring that only distinct values are included in the final result set.

**SQL Query:**

```sql
SELECT fname 
FROM characters
UNION 
SELECT book_name 
FROM library;

  ```

**Result Example**

| fname               |
|----------           |
| Harry               | 
| Hermione            |
| Ron                 |
| The Sorcerer's Stone| 
| Chamber of Secrets  |
| ................... |
