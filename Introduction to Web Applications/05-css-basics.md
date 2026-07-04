# CSS Basics

## 📌 Overview

CSS (**Cascading Style Sheets**) is the stylesheet language used to control the appearance and layout of HTML elements.

While HTML defines the structure of a webpage, CSS defines **how it looks**, including colors, fonts, spacing, positioning, animations, and overall design.

---

# Basic CSS Example

```css
body {
    background-color: black;
}

h1 {
    color: white;
    text-align: center;
}

p {
    font-family: Helvetica;
    font-size: 10px;
}
```

This example:

- Sets the page background to black
- Makes headings white and center-aligned
- Changes paragraph font and size

---

# CSS Syntax

CSS follows a simple structure:

```css
selector {
    property: value;
}
```

Example:

```css
h1 {
    color: blue;
}
```

Where:

- **Selector** → HTML element or class
- **Property** → Style to modify
- **Value** → Assigned style

---

# Common CSS Properties

| Property | Description |
|----------|-------------|
| color | Text color |
| background-color | Background color |
| font-family | Font style |
| font-size | Text size |
| text-align | Text alignment |
| margin | Space outside element |
| padding | Space inside element |
| border | Element border |
| width | Element width |
| height | Element height |
| position | Element positioning |

---

# IDs and Classes

CSS can target elements using **IDs** or **Classes**.

### ID Example

```html
<p id="intro">Welcome</p>
```

```css
#intro {
    color: blue;
}
```

---

### Class Example

```html
<p class="important">Hello</p>
```

```css
.important {
    color: red;
}
```

- `#` → ID selector
- `.` → Class selector

---

# CSS Animations

CSS supports animations without JavaScript.

Common animation properties include:

- `@keyframes`
- `animation`
- `animation-duration`
- `animation-delay`
- `animation-direction`
- `transform`

Example:

```css
.box {
    animation: slide 2s infinite;
}
```

Animations improve user experience by making webpages more interactive.

---

# CSS with JavaScript

JavaScript can dynamically modify CSS properties.

Example:

```javascript
document.body.style.backgroundColor = "black";
```

This allows web applications to:

- Change themes
- Animate elements
- Respond to user actions
- Create dynamic interfaces

---

# CSS Frameworks

Instead of writing all CSS manually, developers often use CSS frameworks.

Popular frameworks include:

| Framework | Purpose |
|-----------|----------|
| Bootstrap | Responsive UI components |
| SASS | CSS preprocessor |
| Foundation | Responsive front-end framework |
| Bulma | Modern Flexbox framework |
| Pure | Lightweight CSS framework |

These frameworks:

- Speed up development
- Provide reusable components
- Improve responsive design
- Maintain consistent styling

---

# Why CSS Matters in Web Security

Although CSS itself is not usually vulnerable, understanding it helps penetration testers:

- Inspect webpage layouts
- Identify hidden elements
- Analyze login forms
- Understand front-end behavior
- Detect UI manipulation techniques

CSS is often used alongside HTML and JavaScript during client-side security testing.

---

# Key Takeaways

- CSS controls the appearance of HTML elements.
- CSS uses the syntax `selector { property: value; }`.
- IDs (`#`) and Classes (`.`) allow targeted styling.
- CSS supports layouts, positioning, colors, fonts, and animations.
- JavaScript can dynamically modify CSS properties.
- CSS frameworks simplify modern web development.

---

# Lab Solution

**Question:**

> What is the CSS "property: value" used to make an HTML element's text aligned to the left?

**Answer:**

```css
text-align: left;
```
