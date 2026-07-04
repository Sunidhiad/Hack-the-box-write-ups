# HTML Basics

## 📌 Overview
HTML (**HyperText Markup Language**) is the foundation of every web page. It defines the structure and content displayed in a web browser, including text, images, forms, buttons, links, and other page elements.

Browsers interpret HTML code and render it into a human-readable webpage.

---

# Basic HTML Structure

Example HTML page:

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Page Title</title>
    </head>
    <body>
        <h1>A Heading</h1>
        <p>A Paragraph</p>
    </body>
</html>
```

Output:

- Page Title
- Heading
- Paragraph

---

# HTML Document Structure

HTML documents follow a tree-like hierarchy.

```
document
 └── html
      ├── head
      │     └── title
      └── body
            ├── h1
            └── p
```

Main sections:

- `<html>` → Root element
- `<head>` → Metadata, title, CSS, scripts
- `<body>` → Visible page content

---

# HTML Tags

Every HTML element is enclosed between an opening and closing tag.

Example:

```html
<p>Hello World</p>
```

Tags can also contain attributes.

Example:

```html
<p id="intro">Hello World</p>
```

Common attributes include:

- id
- class
- style
- src
- href

---

# Common HTML Tags

| Tag | Purpose |
|------|----------|
| `<html>` | Root HTML document |
| `<head>` | Metadata |
| `<title>` | Browser tab title |
| `<body>` | Visible webpage content |
| `<h1>` | Heading |
| `<p>` | Paragraph |
| `<a>` | Hyperlink |
| `<img>` | Display image |
| `<form>` | Form |
| `<input>` | User input |
| `<button>` | Button |
| `<script>` | JavaScript |
| `<style>` | CSS |

---

# URL Encoding (Percent Encoding)

URLs only support ASCII characters.

Special characters are encoded using:

```
% + hexadecimal value
```

Examples:

| Character | Encoding |
|------------|-----------|
| Space | %20 |
| ! | %21 |
| " | %22 |
| # | %23 |
| $ | %24 |
| % | %25 |
| & | %26 |
| ' | %27 |
| ( | %28 |
| ) | %29 |

Example:

```
Hello World
```

becomes

```
Hello%20World
```

Single quote:

```
'
```

becomes

```
%27
```

---

# Document Object Model (DOM)

The browser converts HTML into a **DOM (Document Object Model)**.

The DOM allows JavaScript to access and modify webpage elements dynamically.

Example hierarchy:

```
document
 └── html
      ├── head
      └── body
```

Examples:

```javascript
document.body
```

```javascript
document.head
```

```javascript
document.getElementById("login")
```

---

# Why DOM Matters in Web Security

Understanding the DOM helps penetration testers:

- Inspect webpage source
- Locate forms
- Find hidden elements
- Analyze JavaScript interactions
- Exploit client-side vulnerabilities like XSS

Developers commonly reference elements by:

- ID
- Class
- Tag name

---

# Key Takeaways

- HTML defines the structure of webpages.
- Every webpage follows a hierarchical document structure.
- HTML elements are created using opening and closing tags.
- URLs require percent encoding for special characters.
- Browsers create a DOM from HTML for dynamic interaction.
- DOM knowledge is essential for analyzing front-end behavior during web application security testing.

---

# Lab Solution

**Question:**

> What is the HTML tag used to show an image?

**Answer:**

```html
<img>
```
