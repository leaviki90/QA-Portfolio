# Retrieve Book Titles and Patronus Names Using RIGHT JOIN

**Description:**
This query retrieves book titles from the library table and patronus names from the characters table. It uses a RIGHT JOIN to ensure that all book titles are included in the result set, even if there is no corresponding information about the patronus in the characters table.

**SQL Query:**

```sql
SELECT library.book_name, characters.patronus
FROM characters
RIGHT JOIN library ON characters.char_id = library.char_id;

  ```

**Result Example**

|   book_name           |     patronus        |
|-----------------------|---------------------|
| The Sorcerer's Stone  | Gryffindor          |
| Chamber of Secrets    |  Otter              |
| Prisoner of Azkaban   | Jack Russell Terrier|
| ...                   | ...                 |
