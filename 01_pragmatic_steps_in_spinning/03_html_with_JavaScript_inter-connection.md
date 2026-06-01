# HTML + JavaScript Connection Notes

## Q1: How do I connect JavaScript with HTML?

There are three common ways:

### 1. Internal JavaScript

```html
<!DOCTYPE html>
<html>
<body>

<h1>Hello World</h1>

<script>
    alert("JavaScript Connected!");
</script>

</body>
</html>
```

- JavaScript is written directly inside the `<script>` tag.
- Good for small examples and testing.

---

### 2. External JavaScript (Recommended)

#### index.html

```html
<!DOCTYPE html>
<html>
<body>

<h1>Hello World</h1>

<script src="script.js"></script>

</body>
</html>
```

#### script.js

```javascript
alert("JavaScript Connected!");
```

Project Structure:

```
Project/
│
├── index.html
└── script.js
```

**Why use this?**

- Cleaner code
- Easier maintenance
- Reusable JavaScript

---

### 3. Inline Event Handling

```html
<button onclick="showMessage()">
    Click Me
</button>

<script>
function showMessage() {
    alert("Button Clicked!");
}
</script>
```

---

## Q2: Where should I place the `<script>` tag?

### Option 1 (Common)

```html
<body>

    <!-- Content -->

    <script src="script.js"></script>
</body>
```

### Option 2 (Modern)

```html
<head>
    <script src="script.js" defer></script>
</head>
```

### Which is better?

Using `defer` in `<head>` is considered a modern and recommended approach because:

- HTML loads first
- JavaScript runs afterward
- Prevents DOM loading issues

---

# Connecting JavaScript to HTML Elements

---

## Q3: How do I connect JavaScript with a Button?

### HTML

```html
<button id="btn">Click Me</button>
```

### JavaScript

```javascript
const button = document.getElementById("btn");

button.addEventListener("click", function () {
    alert("Button Clicked!");
});
```

### New Concepts

#### `addEventListener()`

Used to listen for user actions.

Example:

```javascript
button.addEventListener("click", function () {
    console.log("Clicked");
});
```

#### `click`

An event triggered when the button is pressed.

---

## Q4: How do I get data from an Input Field?

### HTML

```html
<input type="text" id="name">
<button id="btn">Show Name</button>
```

### JavaScript

```javascript
const input = document.getElementById("name");
const button = document.getElementById("btn");

button.addEventListener("click", function () {
    alert(input.value);
});
```

### New Concept

#### `.value`

Returns the value entered by the user.

Example:

```javascript
input.value
```

If the user types:

```
Ashik
```

Output:

```
Ashik
```

---

## Q5: How do I change text inside a Div?

### HTML

```html
<div id="demo">Old Text</div>
<button id="btn">Change</button>
```

### JavaScript

```javascript
const div = document.getElementById("demo");
const button = document.getElementById("btn");

button.addEventListener("click", function () {
    div.textContent = "New Text";
});
```

### New Concept

#### `.textContent`

Changes or retrieves visible text.

Example:

```javascript
div.textContent = "Hello";
```

---

## Q6: How do I handle Form Submission?

### HTML

```html
<form id="myForm">
    <input type="text" id="name">
    <button type="submit">Submit</button>
</form>
```

### JavaScript

```javascript
const form = document.getElementById("myForm");

form.addEventListener("submit", function(event) {

    event.preventDefault();

    const name = document.getElementById("name").value;

    console.log(name);
});
```

### New Concept

#### `event.preventDefault()`

Prevents the browser's default action.

Without it:

- Form submits
- Page reloads

With it:

- Page stays
- You control submission behavior

---

## Q7: How do I work with Checkboxes?

### HTML

```html
<input type="checkbox" id="check">
```

### JavaScript

```javascript
const checkbox = document.getElementById("check");

checkbox.addEventListener("change", function () {

    if (checkbox.checked) {
        console.log("Checked");
    } else {
        console.log("Unchecked");
    }

});
```

### New Concepts

#### `.checked`

Returns:

```javascript
true
```

or

```javascript
false
```

depending on checkbox state.

---

## Q8: How do I work with Dropdown Menus?

### HTML

```html
<select id="country">
    <option>Bangladesh</option>
    <option>India</option>
    <option>Nepal</option>
</select>
```

### JavaScript

```javascript
const country = document.getElementById("country");

country.addEventListener("change", function () {
    console.log(country.value);
});
```

### New Concept

#### `change`

Triggered when the selected option changes.

---

# DOM Selection Methods

---

## Q9: How do I select HTML elements?

### By ID

```javascript
document.getElementById("id");
```

### By Class

```javascript
document.getElementsByClassName("class");
```

### By Tag Name

```javascript
document.getElementsByTagName("p");
```

### By CSS Selector

```javascript
document.querySelector(".class");
```

### Multiple Elements

```javascript
document.querySelectorAll(".class");
```

---

## Q10: How do I handle multiple buttons?

### HTML

```html
<button class="btn">One</button>
<button class="btn">Two</button>
<button class="btn">Three</button>
```

### JavaScript

```javascript
const buttons = document.querySelectorAll(".btn");

buttons.forEach(button => {

    button.addEventListener("click", function () {

        console.log(button.textContent);

    });

});
```

### New Concepts

#### `querySelectorAll()`

Returns all matching elements.

#### `forEach()`

Loops through every selected element.

---

# Events Cheat Sheet

| Element | Common Event |
|----------|-------------|
| Button | click |
| Input | input |
| Input | change |
| Form | submit |
| Checkbox | change |
| Select | change |
| Page | load |

---

# Curiosity Section

---

## Q11: Which is better for JavaScript connection: `id` or `class`?

### Short Answer

| Situation | Use |
|------------|------|
| One specific element | id |
| Multiple similar elements | class |

---

## Using ID

### HTML

```html
<input id="username">
```

### JavaScript

```javascript
const user = document.getElementById("username");
```

### Advantages

- Fast
- Unique
- Easy to understand

---

## Using Class

### HTML

```html
<button class="btn">Save</button>
<button class="btn">Delete</button>
<button class="btn">Edit</button>
```

### JavaScript

```javascript
const buttons = document.querySelectorAll(".btn");
```

### Advantages

- Reusable
- Select multiple elements
- Great for styling

---

## Q12: Can an element have both ID and Class?

Yes.

```html
<button id="submitBtn" class="btn primary">
    Submit
</button>
```

### JavaScript

```javascript
document.getElementById("submitBtn");
```

### CSS

```css
.btn {
    padding: 10px;
}

.primary {
    background: blue;
}
```

---

## Q13: What is the modern best practice?

### HTML

```html
<input id="name">

<button class="action-btn">
    Save
</button>

<button class="action-btn">
    Delete
</button>

<button class="action-btn">
    Update
</button>
```

### Rule of Thumb

- Single element → `id`
- Multiple similar elements → `class`
- Styling → `class`
- JavaScript targeting one element → `id`

---

# Final Takeaway

Master these concepts first:

1. `getElementById()`
2. `querySelector()`
3. `querySelectorAll()`
4. `addEventListener()`
5. `.value`
6. `.textContent`
7. `.checked`
8. `event.preventDefault()`

These cover roughly 80% of beginner-to-intermediate HTML + JavaScript interactions.