# 03 — `<div>` vs `<section>` vs `<article>`

## The One-Line Rule

| Tag | Ask yourself... |
|---|---|
| `<div>` | "I just need a box for styling/layout" |
| `<section>` | "This is a themed chunk of the page" |
| `<article>` | "This could stand alone outside this page" |

---

## `<div>` — No Meaning, Just a Box

Use when you only need to **group things for CSS or flexbox**. Carries zero semantic meaning.

```html
<div class="card-grid">
  <div class="card">Card 1</div>
  <div class="card">Card 2</div>
</div>
```

✅ Use when: wrapping items for layout, styling, spacing
❌ Not for: meaningful content grouping

---

## `<section>` — A Themed Zone

Use when content belongs to a **named theme or topic** on the page. Should almost always have a heading inside it.

```html
<section>
  <h2>Our Features</h2>
  <p>Here is what we offer...</p>
</section>
```

✅ Use when: Hero, Features, Testimonials, Pricing zones
❌ Not for: random grouping just to apply CSS

---

## `<article>` — Self-Contained Content

Use when content **makes complete sense on its own** — if copy-pasted elsewhere, it would still make sense.

```html
<article>
  <h2>How to Learn HTML</h2>
  <p>Published April 28, 2026</p>
  <p>HTML is the backbone of the web...</p>
</article>
```

✅ Use when: blog posts, news articles, product cards, comments
❌ Not for: page sections that depend on surrounding context

---

## Side by Side Comparison

```html
<main>

  <section>                      <!-- "Latest Posts" themed zone -->
    <h2>Latest Posts</h2>

    <article>                    <!-- one standalone blog post -->
      <h3>Post Title One</h3>
      <p>Post content here...</p>
    </article>

    <article>                    <!-- another standalone post -->
      <h3>Post Title Two</h3>
      <p>Post content here...</p>
    </article>

  </section>

</main>
```

---

## The Litmus Tests

**Is it a `<div>`?**
> "I just need this wrapper to apply flexbox or a background color."

**Is it a `<section>`?**
> "This block has a clear topic and belongs as a named part of this page."

**Is it an `<article>`?**
> "Could I publish this piece of content on its own page or RSS feed and it would still make sense?" → Yes = `<article>`

---

## Quick Cheat Sheet

```
Whole page region      → <header>, <main>, <footer>
Themed content zone    → <section>
Self-contained piece   → <article>
Layout/styling wrapper → <div>
Inline wrapper         → <span>
```

---

## Flexibility Scale

```
Most flexible  →  <div>       can hold almost anything block or inline
               →  <section>   can hold blocks + inline
               →  <p>         inline elements only
Most strict    →  <ul>/<ol>   <li> children ONLY
```
