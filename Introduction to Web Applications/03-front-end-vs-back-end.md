#  Front End vs. Back End

---

# Objective

Understand the differences between front-end and back-end development, the technologies involved, their responsibilities, and common security issues affecting each side of a web application.

---

# Front End

The **front end** is everything the user sees and interacts with inside a web browser.

It runs entirely on the **client-side** and is interpreted by the browser.

The three core front-end technologies are:

- HTML
- CSS
- JavaScript

---

# Front-End Technologies

| Technology | Purpose |
|------------|---------|
| HTML | Defines the structure of the webpage. |
| CSS | Controls styling, colors, layouts, and animations. |
| JavaScript | Adds interactivity and dynamic behavior. |

---

# Front-End Responsibilities

The front end is responsible for:

- Displaying webpage content
- User Interface (UI)
- User Experience (UX)
- Responsive design
- Client-side interactions
- Browser compatibility

A well-designed front end should work across:

- Desktop
- Mobile
- Tablets
- Different browsers

---

# Back End

The **back end** runs on the server and contains the application's core functionality.

Unlike the front end, users do not directly interact with the back-end code.

The back end processes requests, communicates with databases, performs authentication, and returns responses to the client.

---

# Back-End Components

| Component | Description |
|-----------|-------------|
| Back-End Server | Hosts the application and operating system. |
| Web Server | Handles HTTP requests (Apache, NGINX, IIS). |
| Database | Stores application data. |
| Development Framework | Implements the application's business logic. |

---

# Common Back-End Technologies

### Web Servers

- Apache
- NGINX
- IIS

### Databases

Relational Databases

- MySQL
- Microsoft SQL Server
- Oracle
- PostgreSQL

Non-Relational Databases

- MongoDB
- NoSQL

### Development Frameworks

| Language | Framework |
|----------|-----------|
| PHP | Laravel |
| Python | Django |
| Java | Spring |
| C# | ASP.NET |
| JavaScript | Express.js |

---

# Back-End Responsibilities

The back end is responsible for:

- Processing client requests
- Authentication and authorization
- Business logic
- Database communication
- API development
- Third-party integrations
- Cloud services

---

# Front End vs. Back End

| Front End | Back End |
|-----------|----------|
| Runs in the browser | Runs on the server |
| Visible to users | Hidden from users |
| HTML, CSS, JavaScript | PHP, Java, Python, C#, Node.js |
| User Interface | Business Logic |
| Handles user interaction | Processes requests and data |

---

# Securing the Front End

Since front-end code is publicly accessible, it can be reviewed directly from the browser.

Security testing may include:

- HTML review
- JavaScript analysis
- CSS inspection
- Sensitive information disclosure
- Client-side validation bypass

This type of testing is often part of **White Box Penetration Testing** when source code is available.

---

# Securing the Back End

Back-end source code is normally inaccessible.

Testing usually relies on interacting with the application externally.

Common attack techniques include:

- SQL Injection
- Command Injection
- File Inclusion
- Authentication bypass
- Business logic flaws

This approach is known as **Black Box Penetration Testing**.

If source code becomes available (for example through open-source projects or Local File Inclusion), deeper code review becomes possible.

---

# Common Developer Mistakes

Some common mistakes that lead to vulnerabilities include:

- Accepting invalid input
- Plaintext password storage
- Weak passwords
- Unencrypted sensitive data
- Excessive trust in client-side validation
- SQL Injection vulnerabilities
- Remote File Inclusion
- Hardcoded credentials
- Insecure cryptography
- Web Application Firewall (WAF) misconfiguration

---

# OWASP Top 10 (2021)

| No. | Vulnerability |
|-----|---------------|
| 1 | Broken Access Control |
| 2 | Cryptographic Failures |
| 3 | Injection |
| 4 | Insecure Design |
| 5 | Security Misconfiguration |
| 6 | Vulnerable and Outdated Components |
| 7 | Identification and Authentication Failures |
| 8 | Software and Data Integrity Failures |
| 9 | Security Logging and Monitoring Failures |
| 10 | Server-Side Request Forgery (SSRF) |

---

# Penetration Testing Perspective

During a web application assessment:

- Review client-side code whenever possible.
- Test server-side functionality through HTTP requests.
- Identify injection vulnerabilities.
- Assess authentication and authorization mechanisms.
- Verify proper input validation.
- Check for insecure configurations and exposed sensitive data.

---

# Key Takeaways

- The front end runs inside the browser using HTML, CSS, and JavaScript.
- The back end runs on the server and handles business logic, databases, and authentication.
- Front-end code is visible to users, while back-end code is generally hidden.
- White Box testing involves source code review, whereas Black Box testing tests the application externally.
- Common developer mistakes often lead to OWASP Top 10 vulnerabilities.
- Understanding both the front end and back end is essential for effective web application penetration testing.
