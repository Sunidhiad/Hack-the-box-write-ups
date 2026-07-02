# HTB Academy Write-up: HTTP Methods and Status Codes

## Objective

Understand the purpose of HTTP methods, how they are used to interact with web resources, and how HTTP status codes indicate the outcome of a request.

---

# HTTP Methods

HTTP methods (also called HTTP verbs) tell the server what action the client wants to perform on a resource.

## Common HTTP Methods

| Method      | Purpose                                                                         |
| ----------- | ------------------------------------------------------------------------------- |
| **GET**     | Retrieves a resource from the server. Parameters are usually passed in the URL. |
| **POST**    | Sends data to the server, commonly used for forms, logins, and file uploads.    |
| **HEAD**    | Retrieves only the response headers without the response body.                  |
| **PUT**     | Creates or replaces a resource on the server.                                   |
| **DELETE**  | Removes an existing resource from the server.                                   |
| **OPTIONS** | Returns the HTTP methods supported by the server or resource.                   |
| **PATCH**   | Applies partial updates to an existing resource.                                |

---

# HTTP Status Codes

HTTP status codes indicate whether a request was successful or if an error occurred.

## Status Code Classes

| Class   | Description             |
| ------- | ----------------------- |
| **1xx** | Informational responses |
| **2xx** | Successful requests     |
| **3xx** | Redirection messages    |
| **4xx** | Client-side errors      |
| **5xx** | Server-side errors      |

---

# Common HTTP Status Codes

## 200 OK

The request was successfully processed.

Example:

```http
HTTP/1.1 200 OK
```

---

## 302 Found

The requested resource has temporarily moved to another location.

Example:

```http
HTTP/1.1 302 Found
Location: /dashboard
```

---

## 400 Bad Request

The server cannot process the request because it is malformed.

Example:

```http
HTTP/1.1 400 Bad Request
```

---

## 403 Forbidden

The server understands the request but refuses access.

Example:

```http
HTTP/1.1 403 Forbidden
```

---

## 404 Not Found

The requested resource does not exist.

Example:

```http
HTTP/1.1 404 Not Found
```

---

## 500 Internal Server Error

An unexpected error occurred while processing the request.

Example:

```http
HTTP/1.1 500 Internal Server Error
```

---

# cURL Examples

## GET Request

```bash
curl http://example.com
```

---

## POST Request

```bash
curl -X POST http://example.com
```

---

## HEAD Request

```bash
curl -I http://example.com
```

---

## DELETE Request

```bash
curl -X DELETE http://example.com
```

---

## OPTIONS Request

```bash
curl -X OPTIONS http://example.com
```

---

# Security Perspective

During web application penetration testing, HTTP methods can reveal unintended functionality.

Examples include:

* **PUT** enabled → May allow unauthorized file uploads.
* **DELETE** enabled → May allow deletion of application resources.
* **OPTIONS** enabled → Reveals supported HTTP methods, useful during reconnaissance.
* **HEAD** requests → Useful for gathering information without downloading the full response.

Testing supported methods is an important part of web application enumeration.

---

# Key Takeaways

* HTTP methods define the action performed on a resource.
* GET and POST are the most commonly used methods.
* PUT, PATCH, and DELETE are widely used in REST APIs.
* HTTP status codes indicate the outcome of every request.
* Status codes are grouped into five categories (1xx–5xx).
* Understanding HTTP methods and status codes is essential for web application security testing.

---

# Summary

HTTP methods specify how clients interact with web resources, while HTTP status codes communicate the result of those requests. During penetration testing, analyzing supported methods and interpreting status codes helps identify application behavior, misconfigurations, and potential security vulnerabilities.
