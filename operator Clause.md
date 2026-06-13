# Operators in SQL WHERE Clause

## Introduction

Operators are used with the `WHERE` clause to filter records from a table based on specific conditions.

```sql
CREATE DATABASE facebook;
USE facebook;
```

---

# 1. AND Operator

The `AND` operator is used when multiple conditions must be true.

### Example

```sql
SELECT name, followers, age
FROM user
WHERE followers >= 100 AND age >= 20;
```

### Explanation

* Displays users whose followers are 100 or more.
* Displays users whose age is 20 or more.
* Both conditions must be satisfied.

---

# 2. OR Operator

The `OR` operator is used when at least one condition must be true.

### Example

```sql
SELECT name, age, followers
FROM user
WHERE age >= 18 OR followers >= 200;
```

### Explanation

* Displays users whose age is 18 or greater.
* Also displays users who have 200 or more followers.
* If either condition is true, the record is displayed.

---

# 3. BETWEEN Operator

The `BETWEEN` operator is used to find values within a specified range.

### Example

```sql
SELECT name, age, followers
FROM user
WHERE followers BETWEEN 100 AND 500;
```

### Explanation

* Displays users whose follower count lies between 100 and 500.
* Both 100 and 500 are included in the result.

---

# 4. IN Operator

The `IN` operator is used when we want to match multiple values in a column.

### Example

```sql
SELECT name, followers, age
FROM user
WHERE email IN (EMAIL1, EMAIL2, EMAIL3);
```

### Explanation

* Checks whether the email matches any value in the list.
* Useful when searching for records associated with known email addresses.

---

# 5. NOT IN Operator

The `NOT IN` operator is used to exclude specific values.

### Example

```sql
SELECT name, followers, age
FROM user
WHERE age NOT IN (20);
```

### Explanation

* Displays users whose age is not 20.
* Excludes all records where age equals 20.

---

# Complete Examples

```sql
SELECT name, followers, age
FROM user
WHERE followers >= 100 AND age >= 20;

SELECT name, age, followers
FROM user
WHERE age >= 18 OR followers >= 200;

SELECT name, age, followers
FROM user
WHERE followers BETWEEN 100 AND 500;

SELECT name, followers, age
FROM user
WHERE email IN (EMAIL1, EMAIL2, EMAIL3);

SELECT name, followers, age
FROM user
WHERE age NOT IN (20);
```

---

# Summary Table

| Operator | Purpose                             |
| -------- | ----------------------------------- |
| AND      | Both conditions must be true        |
| OR       | At least one condition must be true |
| BETWEEN  | Find values within a range          |
| IN       | Match values from a given list      |
| NOT IN   | Exclude specific values             |

---

# Interview Questions

### Q1. What is the purpose of the AND operator?

**Answer:**
It returns records only when all specified conditions are true.

### Q2. What is the purpose of the OR operator?

**Answer:**
It returns records when at least one condition is true.

### Q3. Why do we use BETWEEN?

**Answer:**
To find values that fall within a specified range.

### Q4. What is the use of the IN operator?

**Answer:**
To check whether a value exists in a list of values.

### Q5. What does NOT IN do?

**Answer:**
It excludes records that match the specified values.
