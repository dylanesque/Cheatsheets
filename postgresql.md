# DB ROLES

-Go with the 'principal of least privilege': start with no privileges, and only add new privileges as needed.

# The SELECT statement

- 'Select column AS "<new-name>"' to rename/alias columns

- SELECT CONCAT(first_column, ' ', second_column) AS "new_name" to concatenate columns

- In Postgres, Text is in single quotes, columns are in double quotes

-Aggregate functions include MIN, MAX, COUNT, SUM, and AVG

-Single line comments in SQL are done with two dashes, multi-line are same as multi-line in JavaScript

-Operator precedence is: PEMDAS,, concatentation operators, comparison operators, (IS NULL, LIKE, NOT IN, etc), NOT, AND, OR

- CRUD = CREATE, SELECT, INSERT/UPDATE, DELETE

- Insertion: `INSERT INTO users VALUES(NULL, "drizzydude", "082jf48yr39d31-0d329j", "Dave", "Drizzton");`

- Updating: `Update phone_book set first_name = "Mystery", last_name = "Person";`

- Deleting: DELETE FROM phone_book WHERE first_name = "Jonathan" AND last_name = "Luna"

- Transactions are a way to lump multiple statements together

ordering: `SELECT * FROM books ORDER BY genre, title;`

