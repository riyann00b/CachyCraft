# 🛠️ MariaDB: The Data Crafter's Guide

<div align="center">
  
  [![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white)](https://mariadb.org)
  [![SQL](https://img.shields.io/badge/SQL-F29111?style=for-the-badge&logo=mysql&logoColor=white)](#)
  [![Open Source](https://img.shields.io/badge/Open_Source-3DA639?style=for-the-badge&logo=opensourceinitiative&logoColor=white)](#)

</div>

Greetings, Data Crafter! Welcome to your essential guide for mastering **MariaDB**. This guide will provide you with the blueprints and tools to construct powerful databases, manage your data with precision, and keep your server running smoothly.

---

if not installed yet check database section in readme.md 

## 🔌 Entering the Workshop: Connecting to the Server

Before you can build, you need to enter your workshop. Use the `mariadb` client to connect.

```bash
# Connect as root (you'll be prompted for the password you set)
mariadb -u root -p

# Connect as a specific user to a specific database
mariadb -u [username] -p [database_name]

# Connect to a server on another machine
mariadb -u [username] -p -h [host_address] -P [port_number]
```

Once connected, your prompt will change to `MariaDB [(none)]>`. You're in! To leave, just type `exit` or `quit`.

---

## 📜 Reading the Blueprints: Browsing Databases & Tables

Understand your project's structure before you start building.

-   **`SHOW DATABASES;`**  
    📋 Lists all the databases you have permission to see.

-   **`USE database_name;`**  
    🎯 Selects a database to work with. Your prompt will change to `MariaDB [database_name]>`.

-   **`SHOW TABLES;`**  
    📋 Shows all tables in the currently selected database.

-   **`DESCRIBE table_name;`** (or `DESC table_name;`)  
    🔬 Shows the structure of a table: its columns, data types, and keys. It's like looking at a blueprint of your data structure!

---

## ✨ Crafting with Data: Essential Queries (DML)

This is where you shape your raw materials into something useful.

### SELECT: Querying for Data 🔍

-   **`SELECT * FROM table_name;`**  
    Grabs **everything** from a table. Good for a quick look, but can be slow for large projects.

-   **`SELECT column1, column2 FROM table_name;`**  
    Pulls data from specific columns. Much more efficient!

-   **`SELECT * FROM table_name WHERE condition;`**  
    The `WHERE` clause is your filter! It selects rows based on a condition.
    *Example:* `WHERE status = 'active';`

-   **`SELECT * FROM table_name ORDER BY column_name DESC;`**  
    Sorts your results. Use `ASC` for ascending (A-Z, 1-10) and `DESC` for descending (Z-A, 10-1).

### INSERT: Adding New Records ➕

-   **`INSERT INTO table_name (column1, column2) VALUES ('value1', 'value2');`**  
    Adds a new row of data. Always specify the columns to avoid errors if the table changes!

### UPDATE: Modifying Records ✏️

-   **`UPDATE table_name SET column1 = 'new_value' WHERE condition;`**  
    Modifies existing data.  

> [!WARNING]
>     Without a `WHERE` clause, you will update **EVERY SINGLE ROW** in the table. Always double-check your `WHERE`.

### DELETE: Removing Records 🗑️

-   **`DELETE FROM table_name WHERE condition;`**  
    Removes rows.  

> [!WARNING]
>     **⚠️ WARNING!** Same as `UPDATE`, if you forget the `WHERE` clause, you'll delete **ALL YOUR DATA**. Be careful!

---

## 🏗️ Constructing the Foundation: Creating Structures (DDL)

Every great project needs a solid foundation.

-   **`CREATE DATABASE database_name;`**  
    Creates a new, empty database.

-   **`CREATE TABLE table_name ( ... );`**  
    Builds a new table. Define your columns inside the parentheses.

```sql
CREATE TABLE projects (
	id INT NOT NULL AUTO_INCREMENT,
	name VARCHAR(100),
	status VARCHAR(50),
	due_date DATE,
	PRIMARY KEY (id)
);
```

-   **`ALTER TABLE table_name ADD column_name data_type;`**  
    Adds a new column to an existing table.

-   **`DROP TABLE table_name;`**  
    💥 Demolishes the structure! This permanently deletes a table and all its data.

-   **`DROP DATABASE database_name;`**  
    💥 Wipes the entire project slate clean! This deletes the whole database.

---

## 📋 The Crafter's Cheatsheet

Here’s a quick-reference chart for your workshop.

| Action | Command Syntax |
| :--- | :--- |
| **CONNECT** | `mariadb -u [user] -p` |
| **SHOW DATABASES** | `SHOW DATABASES;` |
| **USE DATABASE** | `USE [db_name];` |
| **SHOW TABLES** | `SHOW TABLES;` |
| **DESCRIBE TABLE**| `DESCRIBE [table_name];` |
| **CREATE DATABASE**| `CREATE DATABASE [db_name];` |
| **CREATE TABLE** | `CREATE TABLE [name] (col_name type, ...);` |
| **DROP TABLE** | `DROP TABLE [table_name];` |
| **ADD COLUMN** | `ALTER TABLE [name] ADD [col_name] type;` |
| **MODIFY COLUMN** | `ALTER TABLE [name] MODIFY [col_name] new_type;` |
| **DROP COLUMN** | `ALTER TABLE [name] DROP COLUMN [col_name];` |
| **SELECT ALL** | `SELECT * FROM [table_name];` |
| **SELECT SPECIFIC**| `SELECT col1, col2 FROM [table_name];` |
| **FILTER** | `... WHERE [condition];` (e.g., `id = 5` or `name LIKE 'A%'`) |
| **SORT** | `... ORDER BY [col_name] [ASC/DESC];` |
| **JOIN TABLES** | `... FROM t1 INNER JOIN t2 ON t1.id = t2.t1_id;` |
| **GROUP RESULTS** | `... GROUP BY [col_name];` |
| **INSERT DATA** | `INSERT INTO [name] (col1) VALUES ('val1');` |
| **UPDATE DATA** | `UPDATE [name] SET col1 = 'new_val' WHERE [condition];` |
| **DELETE DATA** | `DELETE FROM [name] WHERE [condition];` |
| **TRUNCATE TABLE**| `TRUNCATE [table_name];` (Deletes all data, resets auto-increment) |
| **CREATE USER** | `CREATE USER 'user'@'host' IDENTIFIED BY 'pass';` |
| **GRANT PERMS** | `GRANT ALL ON db.* TO 'user'@'host';` |
| **REMOVE USER** | `DROP USER 'user'@'host';` |

Happy crafting, and may your queries always be performant! 🛠️

_Last updated: **September 7, 2025**_
