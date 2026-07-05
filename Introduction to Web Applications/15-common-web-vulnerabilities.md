# Common Web Vulnerabilities

## 🎯 Objective

Learn the most common web application vulnerabilities, understand how they occur, and recognize their impact during penetration testing.

---

# Why It Matters

During a penetration test, public exploits may not always exist. In such cases, testers manually identify vulnerabilities caused by insecure coding practices or configuration mistakes.

Many of these issues are part of the **OWASP Top 10**, making them essential knowledge for every security professional.

---

# 1. Broken Authentication

## What is it?

Broken Authentication allows attackers to bypass the login process or impersonate another user.

### Example

Instead of valid credentials, an attacker submits:

```sql
' OR 0=0 #
```

If the application does not validate input correctly, authentication succeeds without knowing the password.

---

## Impact

- Login without credentials
- Account takeover
- Administrator access
- Complete application compromise

---

# 2. Broken Access Control

## What is it?

Broken Access Control occurs when users can access resources or functionality they should not be authorized to use.

### Example

A normal user accesses:

```
/admin
```

or changes:

```
/profile?id=15
```

to

```
/profile?id=1
```

and views another user's information.

---

## Impact

- Unauthorized data access
- Privilege escalation
- Administrative functionality exposure

---

# 3. Malicious File Upload

## What is it?

Applications allowing file uploads must verify uploaded content.

Without validation, attackers can upload executable files.

### Example

Instead of uploading:

```
image.jpg
```

An attacker uploads:

```
shell.php
```

or bypasses filters using:

```
shell.php.jpg
```

If executed by the server, the attacker gains remote code execution.

---

## Impact

- Remote command execution
- Web shell installation
- Complete server compromise

---

# 4. Command Injection

## What is it?

Some applications execute operating system commands.

If user input is included without sanitization, attackers can inject additional commands.

### Example

Application executes:

```bash
ping 192.168.1.10
```

Attacker supplies:

```text
192.168.1.10 | whoami
```

The server now executes:

```bash
ping 192.168.1.10
whoami
```

---

## Impact

- Execute operating system commands
- Read sensitive files
- Reverse shell
- Full server compromise

---

# 5. SQL Injection (SQLi)

## What is it?

SQL Injection occurs when user input is directly inserted into SQL queries without proper validation.

Example vulnerable code:

```php
$query = "SELECT * FROM users WHERE name LIKE '%$searchInput%'";
```

An attacker can inject SQL syntax instead of a normal username.

Example payload:

```sql
' OR 1=1 --
```

---

## Impact

- Read database contents
- Modify records
- Delete data
- Bypass authentication
- Sometimes execute operating system commands

---

# OWASP Top 10 Mapping

| Vulnerability | Description |
|---------------|-------------|
| Broken Authentication | Bypass login mechanisms |
| Broken Access Control | Access unauthorized resources |
| Malicious File Upload | Upload executable files |
| Command Injection | Execute operating system commands |
| SQL Injection | Execute malicious SQL queries |

---

# Prevention

## Broken Authentication

- Strong authentication
- MFA
- Secure session management
- Account lockout

---

## Broken Access Control

- Server-side authorization checks
- Role-Based Access Control (RBAC)
- Principle of Least Privilege

---

## Malicious File Upload

- Allowlist file extensions
- Validate MIME type
- Rename uploaded files
- Store uploads outside the web root
- Scan files for malware

---

## Command Injection

- Never execute user input directly
- Validate and sanitize input
- Use parameterized APIs instead of shell commands
- Run applications with minimal privileges

---

## SQL Injection

- Parameterized queries
- Prepared statements
- Input validation
- Least privilege database accounts

---

# Key Takeaways

- Broken Authentication bypasses login mechanisms.
- Broken Access Control exposes unauthorized functionality.
- File Upload vulnerabilities can lead to remote code execution.
- Command Injection executes operating system commands.
- SQL Injection targets databases and is one of the most dangerous web vulnerabilities.
- Proper input validation, sanitization, and secure coding practices are the primary defenses.

---

# HTB Question

**Question:** To which vulnerability category does **CVE-2014-6271** belong?

**Answer:**

```
Command Injection
```
