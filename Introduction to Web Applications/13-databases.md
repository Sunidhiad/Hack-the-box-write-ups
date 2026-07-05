# Databases

## 🎯 Objective
Understand how databases store web application data, the differences between SQL and NoSQL databases, and how applications interact with databases.

---

# What is a Database?

A database is the storage layer of a web application.

It stores information such as:

- User accounts
- Passwords
- Blog posts
- Comments
- Images
- Uploaded files
- Product information
- Orders
- Logs

Without databases, modern dynamic web applications would not exist.

---

# Why Databases are Important

Databases allow web applications to:

- Store large amounts of information
- Retrieve data quickly
- Update existing records
- Delete unwanted data
- Support multiple users simultaneously

The database is responsible for making content dynamic for every user.

---

# Types of Databases

There are two major categories:

- Relational Databases (SQL)
- Non-Relational Databases (NoSQL)

---

# Relational Databases (SQL)

Relational databases organize information into:

- Tables
- Rows
- Columns

Each table contains related information.

Example:

## Users Table

| id | username | first_name | last_name |
|----|----------|------------|-----------|
| 1 | admin | John | Smith |
| 2 | alice | Alice | Johnson |

---

## Posts Table

| id | user_id | date | content |
|----|---------|------|----------|
| 1 | 1 | 01-01-2021 | Welcome |
| 2 | 2 | 02-01-2021 | Hello World |

The **user_id** links each post to the correct user.

This relationship between tables is called a **Database Schema**.

---

# Benefits of SQL Databases

- Fast queries
- Structured data
- Strong relationships
- Reliable
- Easy data management

SQL databases work best when data follows a well-defined structure.

---

# Common SQL Databases

| Database | Description |
|-----------|-------------|
| MySQL | Most popular open-source relational database |
| MSSQL | Microsoft's SQL Server |
| Oracle | Enterprise-grade commercial database |
| PostgreSQL | Powerful open-source relational database |

Other examples include:

- SQLite
- MariaDB
- Amazon Aurora
- Azure SQL

---

# NoSQL Databases

NoSQL databases do **not** use:

- Tables
- Rows
- Columns
- Relationships
- Schemas

Instead, they store data using flexible storage models.

---

# Common NoSQL Models

- Key-Value
- Document-Based
- Wide-Column
- Graph

---

# Example Key-Value Storage

```json
{
  "100001": {
    "date": "01-01-2021",
    "content": "Welcome to this web application."
  }
}
```

Each key stores an object or value.

This is similar to a dictionary in Python.

---

# Benefits of NoSQL

- Highly scalable
- Flexible structure
- Easy to modify
- Excellent for rapidly changing datasets
- Ideal for cloud-native applications

---

# Common NoSQL Databases

| Database | Description |
|-----------|-------------|
| MongoDB | Most popular document-based database |
| ElasticSearch | Optimized for searching huge datasets |
| Apache Cassandra | Highly scalable distributed database |

Other examples include:

- Redis
- Neo4j
- CouchDB
- Amazon DynamoDB

---

# SQL vs NoSQL

| SQL | NoSQL |
|------|--------|
| Tables | Documents / Key-Value |
| Fixed Schema | Flexible Schema |
| Relationships | No fixed relationships |
| Structured Data | Semi-structured or Unstructured Data |
| Best for complex queries | Best for scalability |

---

# How Web Applications Use Databases

A typical workflow looks like this:

1. User submits input.
2. Application receives the request.
3. Application queries the database.
4. Database returns matching records.
5. Application displays the results.

---

# Example PHP Database Connection

```php
$conn = new mysqli("localhost", "user", "pass");
```

Create a database:

```php
$sql = "CREATE DATABASE database1";
$conn->query($sql);
```

Query data:

```php
$query = "SELECT * FROM table_1";
$result = $conn->query($query);
```

---

# Example Search Query

```php
$searchInput = $_POST['findUser'];

$query = "SELECT * FROM users WHERE name LIKE '%$searchInput%'";
```

The application searches for users matching the provided input.

---

# Security Perspective

Databases are one of the most common attack targets during penetration testing.

Common database-related vulnerabilities include:

- SQL Injection
- Authentication bypass
- Information disclosure
- Excessive database privileges
- Weak database credentials
- Misconfigured databases

Improper handling of user input can allow attackers to manipulate database queries and access unauthorized data.

---

# HTB Question

### Question

What type of database is Google's Firebase Database?

### Answer

```text
NoSQL
```

---

# Key Takeaways

- Databases store all dynamic web application data.
- SQL databases use tables and relationships.
- NoSQL databases use flexible storage models.
- SQL is best for structured data, while NoSQL excels at scalability and flexibility.
- Databases are a primary target during web application penetration testing, especially through SQL Injection.
