# DB ROLES

-Go with the 'principal of least privilege': start with no privileges, and only add new privileges as needed.

# Design

- If you find yourself repeating string data, you need a relationship of some kind instead

- Never use the logical key as the primary key

- Foreign keys should be integers

- Many to many relationships are modelled with a connection table with two foreign keys

# Types

- CHAR is for small strings where the length is known

- VARCHAR is for longer strings

- Postgres has a NOW() function for dates

- Marking a value as SERIAL makes it auto-increment.

# Creation

Modelling relationships:

```sql
CREATE TABLE make (
    id SERIAL,
    name VARCHAR(128) UNIQUE,
    PRIMARY KEY(id)
);

CREATE TABLE model (
  id SERIAL,
  name VARCHAR(128),
  make_id INTEGER REFERENCES make(id) ON DELETE CASCADE,
  PRIMARY KEY(id)
);
```



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

# Joins

- Inner joins: join where things match

- Cross join: mash all that together

# Subqueries

- A Subquery is a query within a query; while they can be useful in some instances, they're often suboptimal, even when compared to two separate queries.

# Indexes

## Inverse Index

- When the index is given a string instead of a logical key, and it returns ALL rows that match that query, instead of just one.



