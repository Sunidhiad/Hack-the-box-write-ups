# Public Vulnerabilities

## 🎯 Objective

Learn how publicly disclosed vulnerabilities (CVEs) are discovered, scored, and used during web application penetration testing.

---

# Why It Matters

Many web applications use publicly available software such as CMS platforms, frameworks, plugins, web servers, and operating systems.

If these components contain known vulnerabilities, attackers can exploit them without discovering new bugs.

Therefore, one of the first steps during a penetration test is checking for **public vulnerabilities**.

---

# Public CVEs

## What is a CVE?

**CVE (Common Vulnerabilities and Exposures)** is a unique identifier assigned to a publicly disclosed security vulnerability.

Example:

```
CVE-2021-44228
```

(Log4Shell)

Each CVE contains:

- Unique identifier
- Vulnerability description
- Severity score
- References
- Public advisories
- Exploit information (if available)

---

# Finding Public Vulnerabilities

Before searching for exploits, identify the application's version.

Example:

```
WordPress 6.3.1
```

Then search:

```
WordPress 6.3.1 exploit
```

or

```
CVE WordPress 6.3.1
```

Version information may be found in:

- Page source
- Login page
- HTTP headers
- README files
- version.php
- GitHub repository
- Error messages

---

# Public Exploit Databases

Common sources include:

| Platform | Purpose |
|----------|----------|
| Exploit-DB | Public exploit repository |
| Rapid7 DB | Vulnerability database |
| Vulnerability Lab | Security advisories |
| NVD | Official CVE database |

---

# What Should We Prioritize?

Focus on vulnerabilities that are:

- CVSS score **8–10**
- Remote Code Execution (RCE)
- Authentication Bypass
- SQL Injection
- File Upload
- Privilege Escalation

These typically have the greatest security impact.

---

# CVSS (Common Vulnerability Scoring System)

## What is CVSS?

CVSS is an industry-standard scoring system used to measure the severity of security vulnerabilities.

Scores range from:

```
0.0 → 10.0
```

Higher scores indicate greater risk.

---

# CVSS v2 Ratings

| Severity | Score |
|-----------|-------|
| Low | 0.0 – 3.9 |
| Medium | 4.0 – 6.9 |
| High | 7.0 – 10.0 |

---

# CVSS v3 Ratings

| Severity | Score |
|-----------|-------|
| None | 0.0 |
| Low | 0.1 – 3.9 |
| Medium | 4.0 – 6.9 |
| High | 7.0 – 8.9 |
| Critical | 9.0 – 10.0 |

---

# CVSS Metrics

CVSS scores are calculated using three metric groups:

## 1. Base Metrics

Measures the inherent characteristics of the vulnerability.

Examples:

- Attack Vector
- Attack Complexity
- Privileges Required
- User Interaction
- Confidentiality Impact
- Integrity Impact
- Availability Impact

---

## 2. Temporal Metrics

Reflect factors that change over time, such as:

- Exploit availability
- Patch availability
- Vendor fixes

---

## 3. Environmental Metrics

Adjust the score based on the organization's environment.

Example:

- Critical production server
- Internal lab system
- Sensitive customer data

---

# Vulnerabilities Beyond the Web Application

Public vulnerabilities are not limited to web applications.

Always check:

- Web servers
- Operating systems
- Plugins
- Frameworks
- Libraries
- Database servers

A vulnerable third-party component can compromise the entire application.

---

# Example: Shellshock

One of the most famous web server vulnerabilities is:

```
Shellshock
```

It affected vulnerable Apache servers using Bash.

Impact:

- Remote command execution
- Full server compromise

---

# Internal vs External Vulnerabilities

## External

Can be exploited directly over the Internet.

Examples:

- Remote Code Execution
- Authentication Bypass
- SQL Injection

---

## Internal

Require access to the internal network or server.

Examples:

- Privilege Escalation
- Local File Inclusion
- Local kernel vulnerabilities

Although not externally reachable, they are still critical once an attacker gains initial access.

---

# Penetration Testing Workflow

1. Identify the application's version.
2. Identify plugins, frameworks, and third-party components.
3. Search for matching CVEs.
4. Check CVSS severity.
5. Look for public Proof-of-Concept (PoC) exploits.
6. Verify the vulnerability in a safe testing environment.
7. Document findings and recommend patches.

---

# Key Takeaways

- CVEs are publicly disclosed security vulnerabilities with unique identifiers.
- Identifying software versions is the first step in finding known vulnerabilities.
- CVSS measures vulnerability severity on a scale from 0.0 to 10.0.
- Prioritize Critical (9.0–10.0) and High (8.0+) vulnerabilities.
- Public exploit databases accelerate vulnerability assessment.
- Always assess web applications **and** their supporting components for known vulnerabilities.

---

# HTB Question

**Question:** What is the CVSS v2.0 score of **CVE-2017-0144**?

**Answer:**

```
9.3
```
