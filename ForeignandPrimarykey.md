# Primary Key and Foreign Key in SQL

## What is a Primary Key?

A **Primary Key** is a column (or set of columns) that uniquely identifies each row in a table.

### Properties of a Primary Key

* Values must be unique.
* Cannot contain NULL values.
* Each table can have only one Primary Key.
* Used to identify records uniquely.

---

## Ways to Create a Primary Key

### Method 1

```sql id="pk1"
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(50)
);
```

### Method 2

```sql id="pk2"
CREATE TABLE users (
    id INT,
    name VARCHAR(50),
    PRIMARY KEY (id)
);
```

Both methods produce the same result.

---

## Example

```sql id="pk3"
CREATE TABLE users (
    id INT,
    age INT,
    name VARCHAR(50) NOT NULL,
    email VARCHAR(50) UNIQUE,
    followers INT DEFAULT 0,
    following INT DEFAULT 0,
    PRIMARY KEY (id)
);
```

### Valid Data

| id | name      |
| -- | --------- |
| 1  | Shubham   |
| 2  | Vaishnavi |

### Invalid Data

| id | name      |
| -- | --------- |
| 1  | Shubham   |
| 1  | Vaishnavi |

❌ Error because the Primary Key value cannot be duplicated.

---

# What is a Foreign Key?

A **Foreign Key** is a column that creates a relationship between two tables.

It refers to the Primary Key of another table.

### Purpose

* Maintains data integrity.
* Prevents invalid references.
* Connects related tables.

---

## Syntax

```sql id="fk1"
FOREIGN KEY (column_name)
REFERENCES parent_table(primary_key_column);
```

### Example

```sql id="fk2"
FOREIGN KEY (user_id)
REFERENCES users(id);
```

Here:

* `user_id` → Foreign Key in the child table.
* `users(id)` → Primary Key in the parent table.

---

# Parent Table

```sql id="fk3"
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(50)
);
```

---

# Child Table

```sql id="fk4"
CREATE TABLE post (
    id INT PRIMARY KEY,
    content VARCHAR(50),
    user_id INT,
    FOREIGN KEY (user_id) REFERENCES users(id)
);
```

---

# Relationship Example

### users Table

| id | name      |
| -- | --------- |
| 1  | Shubham   |
| 2  | Vaishnavi |

### post Table

| id  | content      | user_id |
| --- | ------------ | ------- |
| 101 | Hello World  | 1       |
| 102 | Learning SQL | 2       |

Here:

* `users.id` is the Primary Key.
* `post.user_id` is the Foreign Key.
* Each post belongs to a valid user.

---

# Invalid Example

```sql id="fk5"
INSERT INTO post
VALUES (103, 'New Post', 10);
```

❌ Error if user with ID 10 does not exist in the users table.

---

# Common Error

### Using Reserved Keyword

```sql id="fk6"
CREATE TABLE user (
    id INT PRIMARY KEY
);
```

`user` is a MySQL reserved keyword and may cause issues.

### Better Practice

```sql id="fk7"
CREATE TABLE users (
    id INT PRIMARY KEY
);
```

Then:

```sql id="fk8"
CREATE TABLE post (
    id INT PRIMARY KEY,
    content VARCHAR(50),
    user_id INT,
    FOREIGN KEY (user_id) REFERENCES users(id)
);
```

---

# Primary Key vs Foreign Key

| Feature                  | Primary Key               | Foreign Key                         |
| ------------------------ | ------------------------- | ----------------------------------- |
| Purpose                  | Uniquely identifies a row | Creates relationship between tables |
| Unique Values            | Yes                       | No                                  |
| NULL Allowed             | No                        | Yes (unless specified otherwise)    |
| Number Per Table         | One                       | Multiple                            |
| References Another Table | No                        | Yes                                 |

---

# Interview Questions

### Q1. What is a Primary Key?

A Primary Key uniquely identifies each record in a table.

---

### Q2. Can a Primary Key contain NULL values?

No.

---

### Q3. What is a Foreign Key?

A Foreign Key is a column that references the Primary Key of another table.

---

### Q4. Why do we use Foreign Keys?

* To maintain relationships between tables.
* To ensure data consistency.
* To prevent invalid data entries.

---

# Complete Example

```sql id="fk9"
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(50)
);

CREATE TABLE post (
    id INT PRIMARY KEY,
    content VARCHAR(50),
    user_id INT,
    FOREIGN KEY (user_id) REFERENCES users(id)
);
```
