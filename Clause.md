# SQL Clause (WHERE Clause)

## What is a Clause?

A clause is used to filter data from a table based on a specific condition.

Instead of displaying all records, a clause allows us to retrieve only the records that satisfy the given condition.

---

## WHERE Clause

The `WHERE` clause is used to filter rows according to a condition.

### Syntax

```sql id="cl1"
SELECT column_name
FROM table_name
WHERE condition;
```

---

## Example 1: Display All Details

Suppose we want to view all information of users who have 200 or more followers.

```sql id="cl2"
SELECT *
FROM user
WHERE followers >= 200;
```

### Explanation

* `SELECT *` displays all columns.
* `FROM user` selects the user table.
* `WHERE followers >= 200` filters only those users who have 200 or more followers.

---

## Example 2: Display Only Names

If we only want the names of users who have 100 or more followers, we can select only the `name` column.

```sql id="cl3"
SELECT name
FROM user
WHERE followers >= 100;
```

### Explanation

* `SELECT name` displays only the name column.
* `WHERE followers >= 100` filters users with 100 or more followers.

---

## Example Output

| name      |
| --------- |
| Shubham   |
| Vaishnavi |

---

## Complete Example

```sql id="cl4"
SELECT *
FROM user
WHERE followers >= 200;

SELECT name
FROM user
WHERE followers >= 100;
```

---

## Key Points

* A clause helps filter records from a table.
* The `WHERE` clause is used to apply conditions.
* `SELECT *` displays all columns.
* `SELECT column_name` displays only specific columns.
* Filtering data makes queries more precise and useful.

---

## Interview Question

### Q. Why do we use the WHERE clause?

**Answer:**

The `WHERE` clause is used to filter records and display only those rows that satisfy a specified condition.



