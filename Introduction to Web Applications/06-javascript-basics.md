# JavaScript Basics

## 📌 Overview

JavaScript (JS) is one of the world's most widely used programming languages. It powers the **functionality and interactivity** of web applications.

While:

- **HTML** defines the structure
- **CSS** defines the appearance

**JavaScript controls the behavior** of the webpage.

Without JavaScript, webpages would mostly be static with very limited user interaction.

---

# Adding JavaScript to HTML

JavaScript can be written directly inside an HTML page.

```html
<script type="text/javascript">
    // JavaScript code
</script>
```

It can also be loaded from an external file.

```html
<script src="./script.js"></script>
```

Using external files keeps code organized and reusable.

---

# Basic JavaScript Example

```javascript
document.getElementById("button1").innerHTML = "Changed Text!";
```

This code:

- Finds the HTML element with ID **button1**
- Changes its displayed text to:

```
Changed Text!
```

---

# Common JavaScript Tasks

JavaScript is responsible for many interactive features, including:

- Handling button clicks
- Validating forms
- Updating webpage content
- Creating animations
- Displaying pop-ups
- Processing user input
- Communicating with servers

---

# JavaScript and the DOM

JavaScript interacts with the **Document Object Model (DOM)** to modify webpage elements dynamically.

Example:

```javascript
document.getElementById("username")
```

Other common DOM methods:

```javascript
document.getElementById()
```

```javascript
document.getElementsByClassName()
```

```javascript
document.querySelector()
```

```javascript
document.querySelectorAll()
```

These methods allow JavaScript to find and manipulate HTML elements.

---

# JavaScript and HTTP Requests

JavaScript can communicate with back-end servers without reloading the page.

This is commonly done using:

- AJAX
- Fetch API
- XMLHttpRequest

Example:

```javascript
fetch("/api/users")
```

This enables:

- Live search
- Login systems
- Notifications
- Chat applications
- Dynamic content updates

---

# Browser JavaScript Engine

Modern browsers include built-in JavaScript engines that execute JavaScript directly on the client side.

Examples:

| Browser | JavaScript Engine |
|----------|-------------------|
| Chrome | V8 |
| Edge | V8 |
| Firefox | SpiderMonkey |
| Safari | JavaScriptCore |

Because execution happens inside the browser, webpages become faster and more responsive.

---

# JavaScript Frameworks

Large web applications rarely use plain JavaScript alone.

Developers use frameworks that simplify development and provide reusable components.

Common JavaScript frameworks:

| Framework | Purpose |
|-----------|----------|
| Angular | Full front-end framework |
| React | UI library for building interfaces |
| Vue | Lightweight front-end framework |
| jQuery | Simplifies DOM manipulation and AJAX |

These frameworks reduce development time and improve maintainability.

---

# Why JavaScript Matters in Web Security

JavaScript plays a major role in penetration testing because many client-side vulnerabilities involve JavaScript.

Understanding JavaScript helps identify:

- Cross-Site Scripting (XSS)
- DOM-based XSS
- Client-side validation bypasses
- Hidden functionality
- API endpoints
- Sensitive information exposed in scripts

Many security assessments begin by reviewing JavaScript files loaded by the application.

---

# Key Takeaways

- JavaScript adds functionality and interactivity to webpages.
- It is included using the `<script>` tag.
- JavaScript manipulates webpage elements through the DOM.
- It can communicate with servers using AJAX or the Fetch API.
- Modern browsers execute JavaScript locally for better performance.
- Frameworks like React, Angular, Vue, and jQuery simplify web development.
- Understanding JavaScript is essential for client-side web security testing.
```
