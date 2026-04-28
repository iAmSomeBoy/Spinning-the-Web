# 02 — Block vs Inline vs Inline-Block

## The Three Display Types

| Type | Stacks | Takes full width? | Examples |
|---|---|---|---|
| **Block** | Vertically ↕ | ✅ Yes, full row | `<div>`, `<p>`, `<section>`, `<h1>`–`<h6>`, `<ul>`, `<li>`, `<article>`, `<header>`, `<main>`, `<footer>` |
| **Inline** | Horizontally ↔ | ❌ Only content width | `<span>`, `<a>`, `<strong>`, `<em>` |
| **Inline-block** | Horizontally ↔ | ❌ Only content width, but respects width/height | `<img>`, `<button>`, `<input>` |

---

## Visual Behaviour

### Block — stacks vertically, full width:
```
[          <div>           ]
[           <p>            ]
[          <h1>            ]
```

### Inline — sits side by side, only as wide as content:
```
[<span>] [<a>] [<strong>]
```

### Inline-block — sits side by side, but respects size:
```
[<img>] [<button>] [<input>]
```

---

## Full Tag Lists

### Block Tags ↕ (vertical, full width):
```
<div>        <p>          <h1>–<h6>
<section>    <article>    <aside>
<header>     <footer>     <main>
<nav>        <ul>         <ol>
<li>         <form>       <table>
<figure>     <blockquote>
```

### Inline Tags ↔ (horizontal, content width only):
```
<span>       <a>          <strong>
<em>         <label>      <code>
<small>      <sub>        <sup>
```

### Inline-Block Tags ↔ (horizontal, respects width & height):
```
<img>        <button>     <input>
<select>     <textarea>
```

---

## The Nesting Rule

**Block can hold block OR inline:**
```html
✅ <div>
     <p>text</p>        ← block inside block ✅
     <span>word</span>  ← inline inside block ✅
   </div>
```

**Inline can ONLY hold inline:**
```html
✅ <p>Hello <span>world</span></p>

❌ <p>Hello <div>world</div></p>    ← block inside inline — WRONG
❌ <span><p>text</p></span>         ← block inside inline — WRONG
```

---

## Key Takeaway

> **Block** = owns the whole horizontal line, stacks vertically
> **Inline** = shares the line with neighbors, flows horizontally
> **Inline-block** = shares the line BUT respects width & height

---

## CSS Hint 💡
CSS can override any element's default display type:
```css
span { display: block; }   /* makes inline behave like block */
div  { display: inline; }  /* makes block behave like inline */
div  { display: flex; }    /* turns div into a flex container */
```
