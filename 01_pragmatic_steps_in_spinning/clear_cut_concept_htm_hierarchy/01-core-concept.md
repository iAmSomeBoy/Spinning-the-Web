# 01 — Core Concept of HTML Layout Hierarchy

## What is HTML Structure?

HTML is built on a **tree structure**. Every element lives inside another element, forming parent-child relationships. This is called the **DOM — Document Object Model**.

---

## The Full Document Tree

```
<html>                          ← Root (everything lives here)
 ├── <head>                     ← Metadata (invisible to user)
 │    ├── <title>
 │    ├── <meta>
 │    └── <link> / <style> / <script>
 │
 └── <body>                     ← Visible content
      ├── <header>
      │    └── <nav>
      │         └── <a>
      ├── <main>
      │    ├── <section>
      │    │    ├── <h1>–<h6>
      │    │    ├── <p>
      │    │    └── <div>
      │    │         └── <span>
      │    └── <article>
      ├── <aside>
      └── <footer>
```

---

## The Golden Rules

1. `<html>` is always the root — nothing lives outside it
2. `<head>` and `<body>` are its ONLY direct children
3. `<body>` holds ALL visible content
4. Elements must be **properly closed and nested**

```html
✅ Correct:
<div><p>Hello</p></div>

❌ Wrong (broken nesting):
<div><p>Hello</div></p>
```

---

## Nesting = Parent → Child → Grandchild

```html
<body>                  ← grandparent
  <main>                ← parent
    <section>           ← child
      <p>Content</p>    ← grandchild
    </section>
  </main>
</body>
```

Every arrow of indentation = one level deeper in the tree.

---

## The 3 Tiers of Layout

| Tier | Tags | Role |
|---|---|---|
| 1st — Page regions | `<header>`, `<main>`, `<footer>`, `<nav>`, `<aside>` | Divides the whole page |
| 2nd — Content zones | `<section>`, `<article>` | Divides content inside regions |
| 3rd — Layout & content | `<div>`, `<p>`, `<h1>`–`<h6>`, `<ul>` | Content inside zones |

---

## Semantic vs Generic Tags

- **Semantic** tags tell the browser WHAT the content is: `<header>`, `<main>`, `<article>`, `<footer>`
- **Generic** tags are neutral boxes with no meaning: `<div>` (block), `<span>` (inline)

> Use semantic tags whenever the content has a clear role. Use `<div>`/`<span>` only for layout/styling purposes.
