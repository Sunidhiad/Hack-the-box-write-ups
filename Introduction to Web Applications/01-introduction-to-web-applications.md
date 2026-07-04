# HTB Academy Write-up: Introduction to Web Applications

---

# Objective

Understand what web applications are, how they differ from traditional websites and native applications, why they are widely used, and the common security risks associated with them.

---

# What is a Web Application?

A **web application** is software that runs inside a web browser and follows a **client-server architecture**.

- The **client** (browser) displays the user interface.
- The **server** processes requests, executes application logic, and interacts with databases.

Examples include:

- Gmail
- Amazon
- Google Docs
- Hack The Box

Unlike static websites, web applications provide dynamic and interactive content based on user actions.

---

# Client-Server Architecture

A web application consists of two main components.

| Component | Description |
|----------|-------------|
| Client | The user's web browser that sends requests and displays responses. |
| Server | Processes requests, executes application logic, and returns data to the client. |

Basic workflow:

```
Browser → HTTP Request → Web Server
Browser ← HTTP Response ← Web Server
```

---

# Websites vs Web Applications

Traditional websites mainly display static information, while web applications provide dynamic functionality.

| Website | Web Application |
|---------|-----------------|
| Static content | Dynamic content |
| Same for every visitor | Personalized content |
| Limited interaction | Interactive functionality |
| Manual updates | Real-time updates |

Static websites are commonly referred to as **Web 1.0**, while interactive applications are known as **Web 2.0**.

---

# Web Applications vs Native Applications

Web applications differ from desktop or mobile applications in several ways.

| Web Application | Native Application |
|----------------|--------------------|
| Runs in a browser | Installed on the operating system |
| Platform independent | Platform specific |
| Updated on the server | Requires software updates |
| No installation required | Installation required |

---

# Advantages of Web Applications

- Platform independent
- Accessible from any device with a browser
- Centralized updates
- No installation required
- Lower maintenance costs
- Easy deployment

---

# Disadvantages of Web Applications

- Dependent on an internet connection
- Limited access to operating system features
- Generally slower than native applications
- Browser compatibility issues

---

# Common Web Applications

### Open Source

- WordPress
- Joomla
- OpenCart

### Proprietary

- Shopify
- Wix
- DotNetNuke

---

# Why Web Applications are Security Targets

Web applications are publicly accessible and often connected to sensitive databases.

A successful attack may expose:

- User credentials
- Customer information
- Corporate data
- Internal systems
- Administrative functionality

Since web applications are frequently updated, new vulnerabilities may be introduced during development.

---

# Common Web Application Vulnerabilities

| Vulnerability | Impact |
|--------------|--------|
| SQL Injection | Database compromise |
| Cross-Site Scripting (XSS) | JavaScript execution in users' browsers |
| File Inclusion | Read sensitive files or execute code |
| Unrestricted File Upload | Remote Code Execution |
| IDOR | Access another user's data |
| Broken Access Control | Privilege escalation |

---

# Real-World Attack Examples

### SQL Injection

Extract database information such as usernames and email addresses.

### File Inclusion

Read application source code and discover hidden functionality.

### Unrestricted File Upload

Upload a malicious file to gain Remote Code Execution (RCE).

### Insecure Direct Object Reference (IDOR)

Modify object identifiers to access another user's resources.

Example:

```
/user/701/edit-profile
```

Changing the ID:

```
/user/702/edit-profile
```

may allow access to another user's profile if authorization is not enforced.

### Broken Access Control

Manipulating request parameters to gain administrator privileges.

Example:

```
roleid=3
```

Changing it to:

```
roleid=1
```

could create an administrator account if proper validation is missing.

---

# Importance of Web Application Security

Web application penetration testing helps identify security weaknesses before attackers can exploit them.

A typical assessment includes:

- Testing front-end technologies (HTML, CSS, JavaScript)
- Enumerating server technologies
- Testing authenticated functionality
- Testing unauthenticated functionality
- Identifying vulnerabilities
- Verifying security controls

Industry-standard methodologies such as the **OWASP Web Security Testing Guide (WSTG)** are commonly followed during assessments.

---

# Key Takeaways

- Web applications run in a browser using a client-server architecture.
- They provide dynamic, interactive functionality unlike traditional websites.
- Web applications are platform independent and centrally managed.
- Because they are internet-facing, they present a large attack surface.
- Common vulnerabilities include SQL Injection, XSS, File Inclusion, IDOR, and Broken Access Control.
- Understanding how web applications work is essential for effective penetration testing.
