# HTB Academy Write-up: CRUD API

---

# Objective

Learn how to interact with REST-style APIs using cURL and perform the four basic CRUD (Create, Read, Update, Delete) operations through different HTTP methods.

---

# What is an API?

An **Application Programming Interface (API)** allows applications to communicate with each other.

Web APIs commonly expose resources through URLs and use HTTP methods to perform different operations.

Example endpoint:

```
http://SERVER_IP/api.php/city/london
```

This endpoint targets the **city** resource with **london** as the selected record.

---

# CRUD Operations

CRUD represents the four primary database operations.

| Operation | HTTP Method | Description |
|-----------|-------------|-------------|
| Create | POST | Creates a new resource. |
| Read | GET | Retrieves existing data. |
| Update | PUT | Modifies an existing resource. |
| Delete | DELETE | Removes a resource. |

---

# Reading Data (GET)

Retrieve a specific resource.

```bash
curl http://SERVER_IP/api.php/city/london
```

Pretty-print the JSON output using **jq**.

```bash
curl -s http://SERVER_IP/api.php/city/london | jq
```

Retrieve all matching cities.

```bash
curl -s http://SERVER_IP/api.php/city/le | jq
```

Retrieve every record.

```bash
curl -s http://SERVER_IP/api.php/city/ | jq
```

---

# Creating Data (POST)

Use the **POST** method to add a new resource.

```bash
curl -X POST \
http://SERVER_IP/api.php/city/ \
-d '{"city_name":"HTB_City","country_name":"HTB"}' \
-H "Content-Type: application/json"
```

Verify the new entry.

```bash
curl -s http://SERVER_IP/api.php/city/HTB_City | jq
```

---

# Updating Data (PUT)

Use the **PUT** method to modify an existing resource.

```bash
curl -X PUT \
http://SERVER_IP/api.php/city/london \
-d '{"city_name":"New_HTB_City","country_name":"HTB"}' \
-H "Content-Type: application/json"
```

Verify the update.

```bash
curl -s http://SERVER_IP/api.php/city/New_HTB_City | jq
```

---

# Deleting Data (DELETE)

Remove a resource using the **DELETE** method.

```bash
curl -X DELETE \
http://SERVER_IP/api.php/city/New_HTB_City
```

Confirm deletion.

```bash
curl -s http://SERVER_IP/api.php/city/New_HTB_City | jq
```

Expected response:

```json
[]
```

---

# JSON Responses

Most REST APIs exchange data using JSON.

Example response:

```json
[
    {
        "city_name": "London",
        "country_name": "(UK)"
    }
]
```

The **jq** utility formats JSON output, making it easier to read during assessments.

---

# Common cURL Commands

| Task | Command |
|------|---------|
| Read | `curl URL` |
| Pretty JSON | `curl -s URL \| jq` |
| Create | `curl -X POST` |
| Update | `curl -X PUT` |
| Delete | `curl -X DELETE` |

---

# Exercise Summary

The lab demonstrated all four CRUD operations through a REST-style API.

Steps performed:

1. Update an existing city to **flag**.

```bash
curl -X PUT \
http://SERVER_IP/api.php/city/london \
-d '{"city_name":"flag","country_name":"HTB"}' \
-H "Content-Type: application/json"
```

2. Delete any city.

```bash
curl -X DELETE \
http://SERVER_IP/api.php/city/Leeds
```

3. Search for the updated city.

```bash
curl -s http://SERVER_IP/api.php/city/flag | jq
```

4. Retrieve the flag.

```
HTB{crud_4p!_m4n!pul4t0r}
```

---

# Key Takeaways

- REST APIs commonly implement CRUD functionality.
- GET retrieves resources from an API.
- POST creates new resources.
- PUT updates existing resources.
- DELETE removes resources.
- JSON is the standard format for exchanging API data.
- The **jq** utility is useful for formatting JSON responses.
- cURL can fully interact with REST APIs from the command line.
