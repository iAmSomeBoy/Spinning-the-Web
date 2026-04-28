# 04 — Parent, Child & Sibling Relationships

## Master Parent → Child Table

| Parent | Allowed Children |
|---|---|
| `<html>` | `<head>`, `<body>` ONLY |
| `<head>` | `<title>`, `<meta>`, `<link>`, `<style>`, `<script>` |
| `<body>` | `<header>`, `<main>`, `<footer>`, `<nav>`, `<aside>`, `<div>`, `<section>` |
| `<header>` | `<nav>`, `<div>`, `<h1>`–`<h6>`, `<img>`, `<span>`, `<a>` |
| `<main>` | `<section>`, `<article>`, `<div>`, `<aside>`, `<h1>`–`<h6>`, `<p>`, `<ul>`, `<img>` |
| `<section>` | `<div>`, `<article>`, `<h1>`–`<h6>`, `<p>`, `<ul>`, `<img>`, `<header>`, `<footer>` |
| `<article>` | `<div>`, `<h1>`–`<h6>`, `<p>`, `<img>`, `<section>`, `<header>`, `<footer>`, `<aside>` |
| `<aside>` | `<div>`, `<p>`, `<h1>`–`<h6>`, `<ul>`, `<nav>`, `<img>` |
| `<div>` | **Anything block-level** — `<div>`, `<p>`, `<section>`, `<article>`, `<ul>`, inline elements |
| `<nav>` | `<a>`, `<ul>`, `<div>` |
| `<ul>` / `<ol>` | `<li>` ONLY |
| `<li>` | Text, inline elements, or nested `<ul>` / `<ol>` |
| `<p>` | Inline ONLY — `<span>`, `<a>`, `<strong>`, `<em>`, `<img>` |
| `<span>` | Inline ONLY — `<a>`, `<strong>`, `<em>`, text |
| `<a>` | Inline ONLY — text, `<span>`, `<img>` |
| `<footer>` | `<div>`, `<nav>`, `<p>`, `<span>`, `<a>` |
| `<h1>`–`<h6>` | Inline ONLY — `<span>`, `<a>`, `<strong>`, `<em>` |

---

## Siblings of `<main>` (direct children of `<body>`)

These tags live **beside** `<main>`, not inside it:

```
<body>
 ├── <header>    ← page header (logo, nav)
 ├── <nav>       ← page-level navigation
 ├── <main>      ← primary content ← YOU ARE HERE
 ├── <aside>     ← sidebar / supplementary content
 └── <footer>    ← page footer
```

### ❌ NOT siblings of `<main>`:
```
<section>   → goes INSIDE main
<article>   → goes INSIDE main
<p>         → content, belongs inside main
<span>      → inline, belongs deep inside
<div>       → technically valid but bad practice at body level
```

---

## Valid Parents of `<aside>`

```
<body>       ← page-level sidebar
<main>       ← sidebar within main content
<section>    ← sidebar within a section
<article>    ← sidebar within an article
<div>        ← inside any generic container
```

### ❌ Invalid parents of `<aside>`:
```
<header>    ← aside does not belong here
<footer>    ← aside does not belong here
<nav>       ← aside does not belong here
<p>         ← block inside inline = wrong
<span>      ← block inside inline = wrong
```

---

## The Two Core Nesting Rules

**Rule 1 — Block can hold block or inline:**
```html
✅ <div>
     <p>text</p>        ← block inside block
     <span>word</span>  ← inline inside block
   </div>
```

**Rule 2 — Inline can ONLY hold inline:**
```html
✅ <p>Hello <span>world</span></p>

❌ <p><div>Hello</div></p>     ← WRONG: block inside inline
❌ <span><p>text</p></span>    ← WRONG: block inside inline
```

---

## `<header>` and `<footer>` Can Repeat!

They are not just page-level — they can be re-used inside any container as that container's own header/footer:

```html
<body>
  <header>...</header>         ← page-level header

  <main>
    <section>
      <header>...</header>     ← section-level header
      <article>
        <header>...</header>   ← article-level header
        <p>Content</p>
        <footer>...</footer>   ← article-level footer
      </article>
      <footer>...</footer>     ← section-level footer
    </section>
  </main>

  <footer>...</footer>         ← page-level footer
</body>
```

---

## Most Common Pattern in Real Homepages

```
main → section → div → content
```

- `<main>` = "this is the primary content area"
- `<section>` = "this is a themed zone within main"
- `<div>` = "this is a layout box for CSS/flexbox"
- content = `<p>`, `<h2>`, `<article>`, `<img>` etc.
