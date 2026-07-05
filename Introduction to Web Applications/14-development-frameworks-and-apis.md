# Development Frameworks & APIs

## 🎯 Objective
Understand the role of web development frameworks, APIs, query parameters, SOAP, and REST in modern web applications.

---

# Why Use Development Frameworks?

Modern web applications are too complex to build completely from scratch.

Development frameworks provide:
- Pre-built authentication
- User registration
- Database integration
- Routing
- Security features
- Faster development

This allows developers to focus on business logic instead of reinventing common features.

---

# Common Development Frameworks

| Framework | Language | Used By |
|-----------|----------|---------|
| Laravel | PHP | Startups, Small Businesses |
| Express | Node.js | PayPal, Uber, IBM |
| Django | Python | Google, Instagram, Mozilla |
| Rails | Ruby | GitHub, Airbnb, Twitch |

> Large companies often use multiple frameworks together rather than relying on a single one.

---

# APIs (Application Programming Interface)

An API is a communication interface between applications.

For web applications, APIs allow the **front end** to communicate with the **back end**.

### Typical Flow

1. User performs an action.
2. Front end sends an API request.
3. Server processes the request.
4. Database is queried if necessary.
5. Server returns a response.
6. Browser displays the result.

---

# Query Parameters

The simplest way to send data to the server is through **GET** or **POST** parameters.

## GET Request

```http
/search.php?item=apples
```

The value is visible inside the URL.

---

## POST Request

```http
POST /search.php HTTP/1.1

item=apples
```

The data is sent inside the HTTP request body.

---

### Why Query Parameters Matter

They allow a single page to process different user inputs.

Examples:

- Search
- Login
- Filtering
- Pagination
- Sorting

---

# Web APIs

A Web API exposes application functionality over HTTP.

Examples:

- Weather APIs
- Payment APIs
- Google Maps API
- Twitter API

Instead of rendering HTML, APIs usually return structured data such as JSON or XML.

---

# SOAP API

SOAP (**Simple Object Access Protocol**) exchanges data using **XML**.

Example:

```xml
<?xml version="1.0"?>

<soap:Envelope>
    <soap:Body>
        <soap:Fault>
        </soap:Fault>
    </soap:Body>
</soap:Envelope>
```

### Characteristics

- XML-based
- Supports complex structured data
- Supports stateful communication
- More verbose
- Common in enterprise environments

---

# REST API

REST (**Representational State Transfer**) is the most widely used API architecture today.

REST uses:

- URLs
- HTTP methods
- JSON responses

Example endpoint:

```text
GET /category/posts/
```

Example JSON response:

```json
{
  "100001": {
    "date": "01-01-2021",
    "content": "Welcome to this web application."
  },
  "100002": {
    "date": "02-01-2021",
    "content": "This is the first post."
  }
}
```

REST is:

- Lightweight
- Easy to understand
- Fast
- Highly scalable

---

# HTTP Methods Used in REST

| Method | Purpose |
|---------|----------|
| GET | Retrieve data |
| POST | Create new data |
| PUT | Create or replace existing data |
| DELETE | Remove data |

---

# REST vs SOAP

| REST | SOAP |
|------|------|
| Uses JSON (commonly) | Uses XML |
| Lightweight | Heavy |
| Faster | Slower |
| Easy to develop | More complex |
| Best for web/mobile apps | Common in enterprise systems |

---

# Security Perspective

As penetration testers, APIs are one of the most important attack surfaces.

Common API vulnerabilities include:

- Broken Authentication
- Broken Authorization
- IDOR
- SQL Injection
- Mass Assignment
- Rate Limiting Issues
- Sensitive Data Exposure
- Improper Input Validation

Always inspect:

- GET parameters
- POST data
- JSON bodies
- API endpoints
- HTTP methods

Many modern applications expose far more functionality through APIs than through the visible website.

---

# HTB Question

### Question

Use GET request:

```text
/index.php?id=0
```

to search for the name of the user with ID number **1**.

### Answer

```text
superadmin
```

---

# Key Takeaways

- Development frameworks speed up web application development.
- APIs allow communication between the client and server.
- Query parameters pass user input to applications.
- SOAP exchanges XML data and is common in enterprise applications.
- REST uses HTTP methods and usually returns JSON.
- APIs are one of the primary attack surfaces during web application penetration testing.
