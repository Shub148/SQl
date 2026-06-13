# SQL Data Types

## What are Data Types?

Data types specify the kind of data that can be stored in a database table column.

They help MySQL:

* Store data efficiently
* Validate input values
* Improve query performance
* Maintain data integrity

---

# Categories of SQL Data Types

1. Numeric Data Types
2. String Data Types
3. Date and Time Data Types
4. Boolean Data Type

---

# 1. Numeric Data Types

Numeric data types are used to store numbers.

## INT

Stores whole numbers without decimal values.

### Syntax

```sql id="s1"
column_name INT
```

### Example

```sql id="s2"
age INT
```

### Values

```text id="s3"
10
25
100
5000
```

---

## FLOAT

Stores decimal numbers with approximate precision.

### Example

```sql id="s4"
salary FLOAT
```

### Values

```text id="s5"
10.5
2500.75
99.99
```

---

## DOUBLE

Stores large decimal values with higher precision than FLOAT.

### Example

```sql id="s6"
price DOUBLE
```

---

# 2. String Data Types

String data types store characters and text.

## CHAR(size)

Stores fixed-length strings.

### Example

```sql id="s7"
gender CHAR(1)
```

### Values

```text id="s8"
M
F
```

---

## VARCHAR(size)

Stores variable-length strings.

### Example

```sql id="s9"
name VARCHAR(50)
```

### Values

```text id="s10"
Shubham
Vaishnavi
JobLelo
```

### Difference Between CHAR and VARCHAR

| CHAR           | VARCHAR           |
| -------------- | ----------------- |
| Fixed Length   | Variable Length   |
| Faster Access  | Saves Space       |
| Wastes Storage | Efficient Storage |

---

## TEXT

Stores large amounts of text.

### Example

```sql id="s11"
description TEXT
```

Used for:

* Blog posts
* Comments
* Product descriptions

---

# 3. Date and Time Data Types

Used to store dates and time values.

## DATE

Stores only date.

### Format

```text id="s12"
YYYY-MM-DD
```

### Example

```sql id="s13"
dob DATE
```

Value:

```text id="s14"
2004-08-15
```

---

## TIME

Stores only time.

### Format

```text id="s15"
HH:MM:SS
```

### Example

```sql id="s16"
login_time TIME
```

Value:

```text id="s17"
10:30:45
```

---

## DATETIME

Stores both date and time.

### Example

```sql id="s18"
created_at DATETIME
```

Value:

```text id="s19"
2026-06-13 10:30:45
```

---

# 4. Boolean Data Type

## BOOLEAN

Stores TRUE or FALSE values.

### Example

```sql id="s20"
is_active BOOLEAN
```

Values:

```text id="s21"
TRUE
FALSE
```

> In MySQL, BOOLEAN is internally stored as TINYINT(1).

---

# Example Table Using Different Data Types

```sql id="s22"
CREATE TABLE student (
    rollno INT,
    name VARCHAR(50),
    age INT,
    cgpa FLOAT,
    gender CHAR(1),
    admission_date DATE
);
```

---

# Example Insert Query

```sql id="s23"
INSERT INTO student
VALUES
(101, 'Shubham', 21, 8.5, 'M', '2024-08-01');
```

---

# Commonly Used Data Types

| Data Type | Usage                |
| --------- | -------------------- |
| INT       | Whole Numbers        |
| FLOAT     | Decimal Numbers      |
| DOUBLE    | Large Decimal Values |
| CHAR      | Fixed-Length Text    |
| VARCHAR   | Variable-Length Text |
| TEXT      | Long Text            |
| DATE      | Date                 |
| TIME      | Time                 |
| DATETIME  | Date and Time        |
| BOOLEAN   | True/False Values    |

---

# Interview Questions

### Q1. Difference between CHAR and VARCHAR?

**Answer:**

* CHAR stores fixed-length strings.
* VARCHAR stores variable-length strings and saves storage space.

### Q2. Which data type is used for storing names?

**Answer:**

```sql id="s24"
VARCHAR
```

### Q3. Which data type stores date and time together?

**Answer:**

```sql id="s25"
DATETIME
```

### Q4. Which data type stores decimal numbers?

**Answer:**

```sql id="s26"
FLOAT or DOUBLE
```
