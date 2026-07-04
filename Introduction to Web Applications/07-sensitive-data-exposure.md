# Sensitive Data Exposure

## 📌 Overview

**Sensitive Data Exposure** occurs when confidential information is unintentionally exposed to users through the client-side of a web application.

Unlike back-end vulnerabilities, these issues usually do **not directly compromise the server**, but they can expose valuable information that attackers can use to gain unauthorized access or perform further attacks.

Commonly exposed information includes:

- Credentials
- API keys
- Tokens
- Hidden URLs
- Developer comments
- Internal paths
- Debugging information

---

# Why It Matters

Everything sent to the browser is visible to the user.

This includes:

- HTML
- CSS
- JavaScript
- Images
- Comments
- Metadata

Attackers often inspect these resources looking for sensitive information that developers accidentally left behind.

---

# Viewing Page Source

Most browsers allow viewing the source code of a webpage.

Methods:

- Right Click → **View Page Source**
- Keyboard Shortcut:

```
Ctrl + U
```

You can also inspect source code using:

- Browser Developer Tools
- Burp Suite
- Proxy tools

---

# Example

A normal login page may look completely secure.

```html
<form action="action_page.php" method="post">

    <div class="container">
        <label><b>Username</b></label>
        <input type="text">

        <label><b>Password</b></label>
        <input type="password">

        <!-- TODO: remove test credentials test:test -->

        <button type="submit">Login</button>
    </div>

</form>
```

Inside the HTML source we find:

```html
<!-- TODO: remove test credentials test:test -->
```

The developer accidentally exposed test credentials.

Even if they were intended only for testing, they may still work.

---

# Common Sensitive Information Found

During source code review, penetration testers commonly look for:

- Hardcoded usernames/passwords
- API keys
- Authentication tokens
- Secret keys
- Hidden directories
- Hidden admin panels
- Backup files
- Developer notes
- Debugging comments
- Internal IP addresses
- Email addresses

---

# Why Attackers Check Page Source First

Reviewing page source is considered **low-hanging fruit** because it is:

- Easy
- Fast
- Requires no authentication
- Often reveals useful information

Many penetration tests begin by reviewing the HTML source before performing deeper testing.

---

# Prevention

Developers should avoid exposing unnecessary information.

Best practices include:

- Remove developer comments before deployment
- Never hardcode credentials
- Never expose API secrets
- Remove debugging information
- Remove unused code
- Remove hidden links not intended for users
- Classify sensitive information before publishing
- Obfuscate JavaScript when appropriate

Only the code required for the application should be sent to users.

---

# Why It Matters in Pentesting

Sensitive Data Exposure can lead to:

- Account compromise
- Privilege escalation
- Discovery of hidden functionality
- Information disclosure
- Further attacks against the application

Reviewing client-side source code is one of the **first steps** during a web application assessment.

---

# Key Takeaways

- Sensitive Data Exposure occurs when confidential information is visible on the client side.
- HTML source code should always be inspected during reconnaissance.
- Developer comments frequently reveal useful information.
- Exposed credentials, API keys, hidden links, and debugging information can aid attackers.
- Proper code review before deployment helps prevent accidental information leakage.

---

# Lab Solution

**Question:**

> Check the above login form for exposed passwords. Submit the password as the answer.

**Answer:**

```
HiddenInPlainSight
```
