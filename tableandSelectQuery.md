# Table Queries in SQL

## What is a Table?

A table is a collection of related data organized into rows and columns.

* **Rows** represent records.
* **Columns** represent attributes of those records.

Example:

| id | name      | followers |
| -- | --------- | --------- |
| 1  | Vaishnavi | 123       |
| 2  | Shweta    | 123       |
| 3  | Shubham   | 1000      |

---

# Step 1: Select a Database

Before creating a table, select the database where the table will be stored.

```sql id="tq1"
USE facebook;
```

---

# Step 2: Create a Table

Create a table named `user`.

```sql id="tq2"
CREATE TABLE user (
    id INT PRIMARY KEY,
    name VARCHAR(30),
    followers INT DEFAULT 0,
    following INT DEFAULT 0,
    age INT,
    CONSTRAINT CHECK (age >= 13)
);
```

### Explanation

| Column    | Data Type   | Description         |
| --------- | ----------- | ------------------- |
| id        | INT         | Unique user ID      |
| name      | VARCHAR(30) | User name           |
| followers | INT         | Number of followers |
| following | INT         | Number of following |
| age       | INT         | User age            |

### Constraints Used

* `PRIMARY KEY` → Ensures unique IDs.
* `DEFAULT 0` → Automatically sets followers/following to 0 if no value is provided.
* `CHECK(age >= 13)` → Only users aged 13 or above are allowed.

---

# Step 3: Insert Records

Use the `INSERT INTO` statement to add data into the table.

```sql id="tq3"
INSERT INTO user
(id, name, followers, following, age)
VALUES
(1, 'Vaishnavi', 123, 1, 21),
(2, 'Shweta', 123, 1, 21),
(3, 'Shubham', 1000, 0, 21);
```

---

# Step 4: View Specific Columns

Use the `SELECT` statement to retrieve data.

```sql id="tq4"
SELECT id, age, followers, following, name
FROM user;
```

### Output

| id | age | followers | following | name      |
| -- | --- | --------- | --------- | --------- |
| 1  | 21  | 123       | 1         | Vaishnavi |
| 2  | 21  | 123       | 1         | Shweta    |
| 3  | 21  | 1000      | 0         | Shubham   |

---

# Select All Columns

To display all columns from a table:

```sql id="tq5"
SELECT * FROM user;
```

---

# Common SELECT Queries

### Display Only Names

```sql id="tq6"
SELECT name
FROM user;
```

### Display Name and Followers

```sql id="tq7"
SELECT name, followers
FROM user;
```

### Display Age Only

```sql id="tq8"
SELECT age
FROM user;
```

---

# Complete Example

```sql id="tq9"
USE facebook;

CREATE TABLE user (
    id INT PRIMARY KEY,
    name VARCHAR(30),
    followers INT DEFAULT 0,
    following INT DEFAULT 0,
    age INT,
    CONSTRAINT CHECK(age >= 13)
);

INSERT INTO user
(id, name, followers, following, age)
VALUES
(1, 'Vaishnavi', 123, 1, 21),
(2, 'Shweta', 123, 1, 21),
(3, 'Shubham', 1000, 0, 21);

SELECT * FROM user;
```

---

# Important Notes

* `USE` selects the database.
* `CREATE TABLE` creates a new table.
* `INSERT INTO` adds records.
* `SELECT` retrieves data from a table.
* `*` means all columns.
* `PRIMARY KEY` ensures uniqueness.
* `CHECK` validates entered values.

---

# Interview Questions

### Q1. What does SELECT * mean?

**Answer:**

```sql id="tq10"
SELECT * FROM user;
```

Returns all columns and all rows from the table.

---

### Q2. What is the difference between SELECT * and SELECT name?

**Answer:**

```sql id="tq11"
SELECT * FROM user;
```

Returns all columns.

```sql id="tq12"
SELECT name FROM user;
```

Returns only the name column.

---

### Q3. Why do we use PRIMARY KEY?

**Answer:**

To uniquely identify each row in a table.

---

### Q4. What does CHECK(age >= 13) do?

**Answer:**

Prevents insertion of users whose age is less than 13.
 ### If we want to used or want to see a unique age or something then we usedthis command - SELECT DISTINCT colomn_name  FROM table_name; here column name which column unique things we want to saw such as age , name , id and what so we used that on the place of column_name
