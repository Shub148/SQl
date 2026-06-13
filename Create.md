# MySQL Basics - Database and Table Creation

## 1. Create a Database

Use the `CREATE DATABASE` statement to create a new database.

```sql
CREATE DATABASE college1;
```

After executing the command, refresh the **SCHEMAS** section in MySQL Workbench to see the newly created database.

### Example

```sql
CREATE DATABASE JobLelo_com;
```

> SQL keywords can be written in uppercase or lowercase. However, uppercase is recommended for better readability.

---

## 2. Delete a Database

Use the `DROP DATABASE` statement to remove an existing database.

```sql
DROP DATABASE college1;
```

### Example

```sql
DROP DATABASE JobLelo_com;
```

> ⚠️ Warning: Dropping a database permanently deletes all tables and data inside it.

---

## 3. Select a Database

Before creating tables, you must select the database you want to work with.

```sql
USE college1;
```

---

## 4. Create a Table

Syntax:

```sql
CREATE TABLE table_name (
    column_name1 datatype,
    column_name2 datatype
);
```

### Example

```sql
CREATE TABLE student (
    rollno INT,
    name VARCHAR(30),
    age INT
);
```

### Explanation

| Column | Data Type   | Description                        |
| ------ | ----------- | ---------------------------------- |
| rollno | INT         | Student Roll Number                |
| name   | VARCHAR(30) | Student Name (up to 30 characters) |
| age    | INT         | Student Age                        |

---

## 5. Insert Data into a Table

Use the `INSERT INTO` statement to add records.

```sql
INSERT INTO student
VALUES
(101, 'Vaishnavi', 21),
(102, 'Shubham', 21);
```

---

## 6. View Data from a Table

Use the `SELECT` statement to retrieve data.

```sql
SELECT * FROM student;
```

### Output

| rollno | name      | age |
| ------ | --------- | --- |
| 101    | Vaishnavi | 21  |
| 102    | Shubham   | 21  |

---

## Complete Example

```sql
CREATE DATABASE college1;

USE college1;

CREATE TABLE student (
    rollno INT,
    name VARCHAR(30),
    age INT
);

INSERT INTO student
VALUES
(101, 'Vaishnavi', 21),
(102, 'Shubham', 21);

SELECT * FROM student;
```

## Key Commands Summary

| Command         | Purpose                          |
| --------------- | -------------------------------- |
| CREATE DATABASE | Create a new database            |
| DROP DATABASE   | Delete a database                |
| USE             | Select a database                |
| CREATE TABLE    | Create a new table               |
| INSERT INTO     | Insert records into a table      |
| SELECT *        | Display all records from a table |

```
```
