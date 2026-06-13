# SQL Constraints

## What are Constraints?

Constraints are rules applied to table columns to control the type of data that can be stored in a database.

They help:

* Maintain data integrity
* Prevent invalid data entry
* Ensure consistency across records

---

# Types of Constraints

## 1. NOT NULL

The `NOT NULL` constraint ensures that a column cannot contain NULL values.

### Example

```sql id="c1"
name VARCHAR(50) NOT NULL
```

### Explanation

A user must provide a value for the `name` column.

❌ Invalid

```sql id="c2"
INSERT INTO user (name)
VALUES (NULL);
```

✅ Valid

```sql id="c3"
INSERT INTO user (name)
VALUES ('Shubham');
```

---

## 2. UNIQUE

The `UNIQUE` constraint ensures that all values in a column are different.

### Example

```sql id="c4"
email VARCHAR(50) UNIQUE
```

### Explanation

Two users cannot register with the same email address.

✅ Valid

```text id="c5"
shubham@gmail.com
vaishnavi@gmail.com
```

❌ Invalid

```text id="c6"
shubham@gmail.com
shubham@gmail.com
```

---

## 3. DEFAULT

The `DEFAULT` constraint provides a predefined value when no value is supplied.

### Example

```sql id="c7"
followers INT DEFAULT 0
```

### Explanation

If the user does not provide a value for followers, MySQL automatically stores `0`.

### Example Insert

```sql id="c8"
INSERT INTO user(name)
VALUES ('Shubham');
```

Output:

```text id="c9"
followers = 0
```

---

## 4. CHECK

The `CHECK` constraint restricts the values that can be entered into a column.

### Example

```sql id="c10"
CHECK(age >= 13)
```

### Explanation

Only users aged 13 or above can register.

✅ Valid

```text id="c11"
Age = 18
```

❌ Invalid

```text id="c12"
Age = 10
```

---

## Named CHECK Constraint

You can provide a custom name for a constraint.

### Example

```sql id="c13"
CONSTRAINT age_check CHECK(age >= 13)
```

Here:

* `age_check` is the constraint name.
* Naming constraints is optional but recommended.

---

## Multiple Conditions in CHECK

You can combine multiple conditions using `AND` or `OR`.

### Example

```sql id="c14"
CONSTRAINT age_city_check
CHECK(age >= 18 AND city = 'Delhi')
```

### Explanation

The record is accepted only if:

* Age is 18 or greater
* City is Delhi

Both conditions must be true.

---

# Create Table with Constraints

```sql id="c15"
USE instagram;

CREATE TABLE user (
    id INT,
    age INT,
    name VARCHAR(50) NOT NULL,
    email VARCHAR(50) UNIQUE,
    followers INT DEFAULT 0,
    following INT DEFAULT 0,
    CONSTRAINT age_check CHECK(age >= 13)
);
```

---

# Example Insert Query

```sql id="c16"
INSERT INTO user
(id, age, name, email)
VALUES
(1, 21, 'Shubham', 'shubham@gmail.com');
```

Output:

```text id="c17"
followers = 0
following = 0
```

Because both columns have default values.

---

# Constraint Summary

| Constraint | Purpose                   |
| ---------- | ------------------------- |
| NOT NULL   | Prevents NULL values      |
| UNIQUE     | Prevents duplicate values |
| DEFAULT    | Sets a default value      |
| CHECK      | Restricts allowed values  |

---

# Real-World Examples

| Scenario                            | Constraint |
| ----------------------------------- | ---------- |
| User name is mandatory              | NOT NULL   |
| Email must be unique                | UNIQUE     |
| New account starts with 0 followers | DEFAULT    |
| Minimum age requirement             | CHECK      |

---

# Interview Questions

### Q1. What is the purpose of constraints?

**Answer:**
Constraints enforce rules on table data to maintain accuracy and consistency.

---

### Q2. Difference between NOT NULL and UNIQUE?

| NOT NULL              | UNIQUE                        |
| --------------------- | ----------------------------- |
| Cannot store NULL     | Cannot store duplicate values |
| Same value can repeat | Values must be different      |

---

### Q3. Can a column have both NOT NULL and UNIQUE?

**Answer:**

Yes.

```sql id="c18"
email VARCHAR(100) NOT NULL UNIQUE
```

---

### Q4. What happens if a value is not provided for a DEFAULT column?

**Answer:**
MySQL automatically inserts the default value.
