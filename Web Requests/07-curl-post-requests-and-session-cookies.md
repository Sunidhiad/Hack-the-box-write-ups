# HTB Academy Write-up: cURL POST Requests and Session Cookies

---

# Objective

Learn how to send **HTTP POST requests** using cURL, authenticate through web login forms, manage **session cookies**, and interact with JSON-based APIs.

---

# HTTP POST Requests

Unlike GET requests, POST requests send data inside the **HTTP request body** instead of the URL.

### Advantages of POST

| Feature | Description |
|---------|-------------|
| Hidden Parameters | Data is sent in the request body instead of the URL. |
| Supports Large Data | Suitable for file uploads and large payloads. |
| Binary Data | Can transmit binary content without URL limitations. |

---

# Sending POST Requests with cURL

Use the **-X POST** option to specify the HTTP method and **-d** to include request data.

```bash
curl -X POST \
-d "username=admin&password=admin" \
http://SERVER_IP
```

Successful authentication returns the authenticated page instead of the login page.

---

# Following Redirects

Some applications redirect users after login.

Use:

```bash
curl -L \
-X POST \
-d "username=admin&password=admin" \
http://SERVER_IP
```

The **-L** option automatically follows HTTP redirects.

---

# Viewing Response Headers

Use **-i** to display response headers.

```bash
curl -i \
-X POST \
-d "username=admin&password=admin" \
http://SERVER_IP
```

Example:

```
HTTP/1.1 200 OK

Set-Cookie: PHPSESSID=xxxxxxxxxxxxxxxx
```

The server issues a session cookie after successful authentication.

---

# Session Cookies

Most web applications use cookies to maintain authenticated sessions.

Example:

```
PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1
```

Once the session cookie is obtained, credentials no longer need to be sent with every request.

---

# Using Cookies with cURL

Use the **-b** option to include a cookie.

```bash
curl \
-b "PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1" \
http://SERVER_IP
```

Equivalent request using an HTTP header:

```bash
curl \
-H "Cookie: PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1" \
http://SERVER_IP
```

---

# JSON POST Requests

Many modern web applications exchange data in JSON format.

Example request body:

```json
{
    "search":"london"
}
```

The request must include the correct Content-Type header.

```bash
curl \
-X POST \
-d '{"search":"london"}' \
-H "Content-Type: application/json" \
http://SERVER_IP/search.php
```

---

# Sending Authenticated JSON Requests

Combine the session cookie with the JSON request.

```bash
curl \
-X POST \
-d '{"search":"london"}' \
-H "Content-Type: application/json" \
-b "PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1" \
http://SERVER_IP/search.php
```

Example response:

```json
[
    "London (UK)"
]
```

---

# Browser Developer Tools

The Network tab can be used to inspect POST requests.

Useful information includes:

- Request Method
- Request URL
- POST Body
- Content-Type
- Session Cookies
- Response Data
- Copy as cURL
- Copy as Fetch

This makes it easy to reproduce requests directly from the terminal.

---

# Exercise Summary

The application used a PHP login form for authentication.

Steps performed:

1. Log in using valid credentials.

```bash
curl -X POST \
-d "username=admin&password=admin" \
http://SERVER_IP
```

2. Obtain the session cookie from the response headers.

```
Set-Cookie: PHPSESSID=...
```

3. Inspect the browser's Network tab to identify the JSON request sent to:

```
/search.php
```

4. Reproduce the request using the authenticated session cookie.

```bash
curl \
-X POST \
-d '{"search":"flag"}' \
-H "Content-Type: application/json" \
-b "PHPSESSID=<SESSION_ID>" \
http://SERVER_IP/search.php
```

5. Retrieve the flag.

```
HTB{p0$t_r3p34t3r}
```

---

# Key Takeaways

- POST requests send data in the request body.
- The **-d** option is used to include POST data.
- Session cookies maintain authenticated user sessions.
- The **-b** option allows cURL to send cookies.
- JSON requests require the **Content-Type: application/json** header.
- Browser DevTools simplify request analysis and reproduction using cURL.

