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

------------------------------------------------------------------------------------------

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

------------------------------------------------------------------------------------------

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

-----------------------------------------------------------------------------------------

# Select Characters with Known Patronus

**Description:**
This query retrieves the first name, last name, and patronus of characters who have a known patronus (i.e., the patronus is not "Unknown" and is not NULL).

**SQL Query:**

```sql
SELECT fname, lname, patronus
FROM characters
WHERE NOT patronus = 'Unknown'
AND patronus IS NOT NULL;
  ```

**Result Example**

| fname   | lname   | patronus               |
|---------|---------|------------------------|
| Harry   | Potter  | Gryffindor             |
| Hermione| Granger | Otter                  |
| Ron     | Weasley | Jack Russell Terrier   |
| ...     | ...     | ...                    |

-----------------------------------------------------------------------------------------

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

