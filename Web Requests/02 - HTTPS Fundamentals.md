# HTB Academy Write-up: HyperText Transfer Protocol Secure (HTTPS)

## Objective

Understand how HTTPS secures HTTP communication by encrypting data exchanged between the client and the server, preventing attackers from reading sensitive information.

---

# What is HTTPS?

HTTPS (HyperText Transfer Protocol Secure) is the secure version of HTTP. It encrypts all communication between a client and a web server using SSL/TLS.

Unlike HTTP, where all transmitted data is sent in plain text, HTTPS ensures confidentiality, integrity, and authentication.

Default Ports:

| Protocol | Port |
| -------- | ---- |
| HTTP     | 80   |
| HTTPS    | 443  |

---

# Why HTTPS is Important

When using HTTP, sensitive information such as:

* Usernames
* Passwords
* Session Cookies
* Personal Data

is transmitted as plain text.

Anyone positioned between the client and server can intercept this traffic using a Man-in-the-Middle (MITM) attack.

HTTPS encrypts all communication, making intercepted traffic unreadable without the encryption keys.

---

# HTTP vs HTTPS

| HTTP                              | HTTPS                          |
| --------------------------------- | ------------------------------ |
| No encryption                     | Encrypted communication        |
| Port 80                           | Port 443                       |
| Vulnerable to packet sniffing     | Protects against eavesdropping |
| Credentials visible in plain text | Credentials are encrypted      |
| No certificate required           | Requires SSL/TLS certificate   |

---

# HTTPS Communication Flow

1. The user enters a website URL.

2. If HTTP is used, the server often redirects the client to HTTPS using:

```
301 Moved Permanently
```

3. The browser starts the TLS handshake.

4. The server sends its SSL/TLS certificate.

5. The client verifies the certificate.

6. Encryption keys are exchanged.

7. An encrypted connection is established.

8. All HTTP traffic is now transmitted securely.

---

# SSL/TLS Handshake (High-Level)

The TLS handshake performs the following:

* Client Hello
* Server Hello
* Certificate Exchange
* Certificate Verification
* Key Exchange
* Secure Encrypted Session

After a successful handshake, all HTTP requests and responses are encrypted.

---

# cURL with HTTPS

cURL automatically supports HTTPS.

Example:

```bash
curl https://example.com
```

If the SSL certificate is valid, cURL establishes a secure connection and returns the response.

---

# Invalid SSL Certificate

If the certificate is invalid or expired, cURL refuses the connection.

Example:

```bash
curl https://example.com
```

Output:

```text
curl: (60) SSL certificate problem
```

This protects users from potential Man-in-the-Middle attacks.

---

# Ignoring SSL Certificate Validation

During penetration testing, development, or lab environments, applications may use self-signed certificates.

To ignore certificate validation:

```bash
curl -k https://example.com
```

The `-k` (`--insecure`) option tells cURL to skip SSL certificate verification.

> **Note:** This option should only be used in testing or trusted environments. Avoid using it against production systems unless you understand the risks.

---

# Key Commands

View a secure webpage:

```bash
curl https://example.com
```

Ignore SSL verification:

```bash
curl -k https://example.com
```

Save the webpage locally:

```bash
curl -k -O https://example.com/index.html
```

Silent mode:

```bash
curl -k -s https://example.com
```

---

# Key Takeaways

* HTTPS encrypts HTTP communication using SSL/TLS.
* HTTP traffic is transmitted in plain text and can be intercepted.
* HTTPS uses port **443**, while HTTP uses port **80**.
* Most websites automatically redirect HTTP requests to HTTPS.
* cURL validates SSL certificates by default.
* The `-k` option bypasses certificate validation for testing purposes.
* Always prefer HTTPS when transmitting sensitive information.

---

# Summary

HTTPS provides secure communication between clients and web servers by encrypting transmitted data. It prevents attackers from viewing credentials, cookies, and other sensitive information during transmission. During penetration testing, cURL's `-k` option can be used to interact with servers using self-signed or invalid certificates, but this should only be done in controlled testing environments.
