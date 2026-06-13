# Database Queries in MySQL

## 1. Create a Database

Use the `CREATE DATABASE` statement to create a new database.

```sql
CREATE DATABASE instagram;
```

---

## 2. Create a Database Only If It Doesn't Exist

The `IF NOT EXISTS` clause prevents errors if the database already exists.

```sql
CREATE DATABASE IF NOT EXISTS instagram;
```

### How It Works

* If the database does not exist → MySQL creates it.
* If the database already exists → MySQL shows a warning and does not create a duplicate database.

---

## 3. Delete a Database

Use the `DROP DATABASE` statement to permanently remove a database.

```sql
DROP DATABASE college1;
```

> ⚠️ Warning: This command permanently deletes the database and all data stored inside it.

---

## 4. Delete a Database Only If It Exists

The `IF EXISTS` clause prevents errors when the specified database is not available.

```sql
DROP DATABASE IF EXISTS college1;
```

### How It Works

* If the database exists → MySQL deletes it.
* If the database does not exist → MySQL does nothing and avoids an error.

---

## 5. Display All Databases

Use the following command to view all available databases.

```sql
SHOW DATABASES;
```

### Example Output

```text
+--------------------+
| Database           |
+--------------------+
| instagram          |
| mysql              |
| information_schema |
| performance_schema |
+--------------------+
```

---

## 6. Select a Database

Before working with tables, you must select the database you want to use.

```sql
USE instagram;
```

After executing this command, all table operations will be performed inside the `instagram` database.

---

## 7. Display All Tables

To view all tables within the currently selected database:

```sql
SHOW TABLES;
```

### Example

```sql
USE instagram;

SHOW TABLES;
```

### Example Output

```text
+------------------+
| Tables_in_instagram |
+------------------+
| users            |
| posts            |
| followers        |
+------------------+
```

---

## Complete Example

```sql
CREATE DATABASE IF NOT EXISTS instagram;

SHOW DATABASES;

USE instagram;

SHOW TABLES;

DROP DATABASE IF EXISTS college1;
```

---

## Summary Table

| Command                               | Purpose                                     |
| ------------------------------------- | ------------------------------------------- |
| CREATE DATABASE db_name               | Create a new database                       |
| CREATE DATABASE IF NOT EXISTS db_name | Create only if it does not exist            |
| DROP DATABASE db_name                 | Delete a database                           |
| DROP DATABASE IF EXISTS db_name       | Delete only if it exists                    |
| SHOW DATABASES                        | Display all databases                       |
| USE db_name                           | Select a database                           |
| SHOW TABLES                           | Display all tables in the selected database |

## Notes

* Database names should be meaningful and easy to understand.
* Always use `IF EXISTS` and `IF NOT EXISTS` in production environments to avoid unnecessary errors.
* `SHOW TABLES` works only after selecting a database using the `USE` statement.
