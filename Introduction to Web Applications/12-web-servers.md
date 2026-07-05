# Web Servers

## 🎯 Objective

Understand the role of **Web Servers**, how they process HTTP requests and responses, common HTTP status codes, and the most widely used web servers in modern web applications.

---

# Overview

A **Web Server** is software that runs on a back-end server and is responsible for handling all HTTP/HTTPS communication between clients and the web application.

Its responsibilities include:

- Receiving HTTP requests
- Routing requests to the correct application or file
- Executing required processes
- Returning HTTP responses
- Serving static and dynamic content

Web servers typically listen on:

- **Port 80** → HTTP
- **Port 443** → HTTPS

---

# Web Server Workflow

A typical request follows this process:

```
Client Browser
      │
      ▼
 Sends HTTP Request
      │
      ▼
   Web Server
      │
      ▼
Processes Request
      │
      ▼
Application / Database
      │
      ▼
 Generates Response
      │
      ▼
Returns HTTP Response
      │
      ▼
Client Browser
```

The web server acts as the bridge between users and the web application's back-end components.

---

# HTTP Response Codes

Every HTTP response contains a status code that indicates the result of the request.

## Successful Responses

| Code | Meaning |
|------|---------|
| 200 OK | Request completed successfully |
| 201 Created | Resource created successfully |

---

## Redirection Responses

| Code | Meaning |
|------|---------|
| 301 Moved Permanently | Resource permanently moved |
| 302 Found | Resource temporarily moved |

---

## Client Error Responses

| Code | Meaning |
|------|---------|
| 400 Bad Request | Invalid request syntax |
| 401 Unauthorized | Authentication required |
| 403 Forbidden | Access denied |
| 404 Not Found | Resource does not exist |
| 405 Method Not Allowed | HTTP method is not allowed |
| 408 Request Timeout | Client request timed out |

---

## Server Error Responses

| Code | Meaning |
|------|---------|
| 500 Internal Server Error | Unexpected server error |
| 502 Bad Gateway | Invalid response from upstream server |
| 504 Gateway Timeout | Upstream server did not respond in time |

---

# Handling User Input

Web servers process various types of incoming data, including:

- Form data
- URL parameters
- JSON
- XML
- File uploads
- Binary data

After receiving a request, the web server forwards it to the appropriate application logic and returns the generated response to the client.

---

# Using cURL

Retrieve only the HTTP response headers:

```bash
curl -I https://academy.hackthebox.com
```

Example response:

```http
HTTP/2 200
Content-Type: text/html
```

---

Retrieve the page source:

```bash
curl https://academy.hackthebox.com
```

Example:

```html
<!doctype html>
<html>
<head>
<title>Cyber Security Training : HTB Academy</title>
```

---

# Popular Web Servers

## Apache

Apache (httpd) is the most widely used web server on the Internet.

### Features

- Open source
- Cross-platform
- Modular architecture
- Excellent documentation
- Highly customizable

### Commonly Used With

- PHP
- Python
- Perl
- .NET
- CGI

### Companies Using Apache

- Apple
- Adobe
- Baidu

---

## NGINX

NGINX is designed for handling a large number of simultaneous connections efficiently.

Instead of creating one process per request, it uses an asynchronous architecture, making it extremely fast and memory efficient.

### Features

- Open source
- High performance
- Low memory usage
- Excellent scalability
- Reverse proxy support
- Load balancing

### Companies Using NGINX

- Google
- Facebook
- Twitter
- Netflix
- Cisco
- Intel
- Hack The Box

---

## IIS (Internet Information Services)

IIS is Microsoft's web server designed primarily for Windows environments.

### Features

- Runs on Windows Server
- Excellent Active Directory integration
- Supports Windows Authentication
- Optimized for ASP.NET applications
- Can also host PHP and FTP services

### Companies Using IIS

- Microsoft
- Office365
- Skype
- Stack Overflow
- Dell

---

# Other Web Servers

Other commonly used web servers include:

- Apache Tomcat (Java)
- Node.js
- Lighttpd
- Caddy

Each is optimized for different development environments and programming languages.

---

# Security Considerations

Since web servers are Internet-facing, they are a common attack target.

Common attacks include:

- Directory Traversal
- File Upload attacks
- HTTP Request Smuggling
- Misconfigurations
- Information Disclosure
- Remote Code Execution
- Denial of Service (DoS)

Regular updates, secure configuration, and proper access controls are essential to reduce risk.

---

# HTB Lab

## Question

If a web server returns an HTTP code **201**, what does it stand for?

### Answer

```
created
```

---

# Key Takeaways

- A web server handles all HTTP/HTTPS communication between clients and applications.
- It receives requests, processes them, and returns HTTP responses.
- Common web servers include Apache, NGINX, and IIS.
- HTTP status codes indicate the result of a request.
- Web servers are critical infrastructure components and frequent targets for security attacks.
