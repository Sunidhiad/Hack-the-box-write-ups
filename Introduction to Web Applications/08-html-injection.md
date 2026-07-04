# HTML Injection

## 📌 Overview

**HTML Injection** occurs when a web application displays **unsanitized user input** as HTML.

Instead of treating user input as plain text, the browser interprets it as HTML code, allowing attackers to modify the webpage's content or appearance.

This vulnerability exists when applications fail to validate or sanitize user input before rendering it.

---

# How HTML Injection Works

A typical flow:

```
User Input
      │
      ▼
Application receives input
      │
      ▼
No validation or sanitization
      │
      ▼
Browser renders input as HTML
      │
      ▼
HTML Injection
```

---

# Example Vulnerable Code

```html
<!DOCTYPE html>
<html>

<body>

<button onclick="inputFunction()">
Click to enter your name
</button>

<p id="output"></p>

<script>

function inputFunction() {

    var input = prompt("Please enter your name","");

    if(input != null){

        document.getElementById("output").innerHTML =
        "Your name is " + input;

    }

}

</script>

</body>
</html>
```

The vulnerable line is:

```javascript
document.getElementById("output").innerHTML =
"Your name is " + input;
```

Because the application directly inserts user input into `innerHTML`, the browser interprets any HTML tags entered by the user.

---

# HTML Injection Example

Input:

```html
<style>
body{
background-image:url('https://academy.hackthebox.com/images/logo.svg');
}
</style>
```

Result:

- Background image changes immediately
- Browser executes the injected HTML
- Page appearance is modified

This is an example of **HTML Injection**.

---

# Possible Attacks

Attackers can use HTML Injection to:

- Modify webpage appearance
- Deface websites
- Display fake login forms
- Insert phishing content
- Display malicious advertisements
- Mislead users

Unlike XSS, HTML Injection alone does **not execute JavaScript**, but it can still be dangerous.

---

# HTML Injection vs XSS

| HTML Injection | Cross-Site Scripting (XSS) |
|----------------|----------------------------|
| Injects HTML elements | Executes JavaScript |
| Changes webpage layout | Executes malicious scripts |
| Usually affects page appearance | Can steal cookies, sessions, tokens |
| Lower impact | Higher impact |

---

# Prevention

Developers should always:

- Validate user input
- Sanitize HTML content
- Encode special characters
- Avoid using `innerHTML` with user input
- Use `textContent` or `innerText` whenever possible

Example (Safe):

```javascript
document.getElementById("output").textContent =
"Your name is " + input;
```

Using `textContent` displays user input as plain text instead of rendering HTML.

---

# Why It Matters in Pentesting

HTML Injection helps penetration testers identify:

- Missing input validation
- Client-side rendering issues
- Potential phishing opportunities
- Misconfigured front-end logic

Although less severe than XSS, HTML Injection can still lead to social engineering attacks and website defacement.

---

# Key Takeaways

- HTML Injection occurs when user input is rendered as HTML.
- It results from missing input validation or sanitization.
- Attackers can modify webpage content or appearance.
- Avoid using `innerHTML` with untrusted input.
- Prefer `textContent` or proper output encoding.
- HTML Injection is often a stepping stone toward discovering more severe vulnerabilities like XSS.

---

# Lab Solution

**Question:**

> What text would be displayed on the page if we use the following payload as our input?

```html
<a href="http://www.hackthebox.com">Click Me</a>
```

**Answer:**

```
Your name is Click Me
```
