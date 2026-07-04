01 - Introduction to Web Applications
Objective

Understand what web applications are, how they differ from traditional websites and native applications, and why web application security is important.

What is a Web Application?

A web application is software that runs inside a web browser using a client-server architecture.

It consists of:

Frontend (Client-side) – HTML, CSS, JavaScript
Backend (Server-side) – PHP, Python, Java, Node.js, databases, APIs

Instead of installing software locally, users interact with the application through their browser.

Examples include:

Gmail
Amazon
Google Docs
GitHub
Hack The Box
Client-Server Architecture
User
   │
Browser
   │
HTTP/HTTPS
   │
Web Server
   │
Application Logic
   │
Database

The browser sends HTTP requests.

The server processes the request and returns a response.

Web Applications vs Websites
Website	Web Application
Static content	Dynamic content
Same for every visitor	Different for each user
Limited interaction	Highly interactive
Mostly informational	Performs business logic

Example:

Website

About Us
Contact
Services

Web Application

Login
Dashboard
Shopping Cart
Search
File Upload
Messaging
Web Applications vs Native Applications
Native Applications
Installed locally
Faster
Access operating system resources
Platform specific

Examples

Microsoft Word
Discord Desktop
VLC
Web Applications
No installation required
Runs in browser
Platform independent
Centralized updates

Examples

Gmail
Google Docs
Trello
Types of Web Applications
Open Source

Source code is publicly available.

Examples:

WordPress
Joomla
OpenCart

Advantages

Free
Customizable
Community support
Closed Source

Owned by companies.

Examples

Shopify
Wix
DotNetNuke

Advantages

Commercial support
Managed updates
Why Are Web Applications Attractive Targets?

Web applications are:

Publicly accessible
Constantly changing
Connected to databases
Store sensitive information

If compromised, attackers may gain:

User credentials
Customer information
Source code
Database access
Remote code execution
Common Web Application Vulnerabilities
SQL Injection (SQLi)

Unsafe user input is executed as SQL queries.

Impact

Read database
Modify records
Authentication bypass
Remote code execution (in some cases)
File Inclusion

Allows attackers to include unintended files.

Impact

Read sensitive files
Execute malicious code
Obtain configuration files
Unrestricted File Upload

Application accepts dangerous file types.

Example

Uploading

shell.php

instead of

image.jpg

Impact

Remote Code Execution
Full server compromise
Insecure Direct Object Reference (IDOR)

User changes object identifiers.

Example

/user/101

↓

/user/102

Impact

Access another user's information.

Broken Access Control

Application fails to enforce permissions.

Example

Changing

role=3

↓

role=1

Impact

Privilege escalation.

Why Learn Web Application Security?

Modern penetration tests focus heavily on web applications because:

Nearly every company exposes web applications
Web vulnerabilities often lead to full compromise
Small coding mistakes can have severe consequences

Understanding web applications is essential for:

Bug Bounty Hunting
Penetration Testing
Application Security
Red Teaming
Typical Web Penetration Testing Workflow
Reconnaissance
        │
        ▼
Technology Identification
        │
        ▼
Directory & File Enumeration
        │
        ▼
Authentication Testing
        │
        ▼
Input Validation Testing
        │
        ▼
Business Logic Testing
        │
        ▼
Exploitation
        │
        ▼
Reporting
Real-World Attack Examples
Vulnerability	Potential Impact
SQL Injection	Dump user database, extract usernames
File Upload	Remote Code Execution
IDOR	Access another user's data
Broken Access Control	Become administrator
File Inclusion	Read configuration files
Key Takeaways
Web applications are dynamic client-server applications.
They differ significantly from static websites.
Most organizations rely on web applications.
Public exposure makes them attractive attack targets.
Understanding web technologies is the foundation of Application Security.
Common vulnerabilities include SQL Injection, IDOR, File Upload, File Inclusion, and Broken Access Control.
Web penetration testing follows a structured methodology beginning with reconnaissance and enumeration.
Skills Learned
Understanding client-server architecture
Difference between websites and web applications
Understanding common web application attack surfaces
Introduction to common web vulnerabilities
Understanding why web application security is important
