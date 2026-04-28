# 05 — Homepage Layout Hierarchy

## The Standard Homepage Skeleton

```
<html>
└── <body>
     ├── <header>          ← Brand + Navigation
     ├── <main>            ← All page content
     │    ├── <section>    ← Hero
     │    ├── <section>    ← Features / About
     │    ├── <section>    ← Testimonials / Pricing
     │    └── <section>    ← CTA (Call to Action)
     └── <footer>          ← Links, copyright, contacts
```

---

## Each Section Explained

### 1. `<header>` — Top Bar
```html
<header>
  <div class="logo">MyBrand</div>
  <nav>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
</header>
```
- Always visible at the top
- Contains logo + navigation links
- Often sticky (stays when you scroll) — CSS handles this

---

### 2. Hero `<section>` — First Impression
```html
<section>
  <h1>Big Bold Headline</h1>
  <p>A short description of what you offer.</p>
  <a href="#">Get Started</a>
</section>
```
- The very first thing visitors see
- Big headline, subtext, and a CTA button
- Often has a background image — CSS handles this

---

### 3. Features `<section>` — What You Offer
```html
<section>
  <h2>Our Features</h2>
  <div>
    <article>
      <h3>Feature 1</h3>
      <p>Description of feature one.</p>
    </article>
    <article>
      <h3>Feature 2</h3>
      <p>Description of feature two.</p>
    </article>
    <article>
      <h3>Feature 3</h3>
      <p>Description of feature three.</p>
    </article>
  </div>
</section>
```
- Usually 3 cards in a row (flexbox makes them horizontal — CSS)
- Each card is an `<article>` (self-contained)

---

### 4. Social Proof `<section>` — Trust
```html
<section>
  <h2>What People Say</h2>
  <article>
    <blockquote>This changed my life!</blockquote>
    <cite>— Happy Customer</cite>
  </article>
</section>
```
- Testimonials, client logos, or stats
- Builds credibility

---

### 5. CTA `<section>` — Final Push
```html
<section>
  <h2>Ready to get started?</h2>
  <p>Join thousands of happy users today.</p>
  <a href="#">Sign Up Free</a>
</section>
```
- Last chance to convert the visitor
- Simple, bold, one button

---

### 6. `<footer>` — Bottom Info
```html
<footer>
  <p>© 2026 MyBrand</p>
  <nav>
    <a href="#">Privacy</a>
    <a href="#">Terms</a>
  </nav>
</footer>
```
- Copyright, legal links, social icons
- Sometimes repeats nav links

---

## Visual Layout

```
┌─────────────────────────────┐
│  HEADER  (logo + nav)       │
├─────────────────────────────┤
│  HERO    (headline + CTA)   │
├─────────────────────────────┤
│  FEATURES  [ ]  [ ]  [ ]   │
├─────────────────────────────┤
│  TESTIMONIALS / PROOF       │
├─────────────────────────────┤
│  CALL TO ACTION             │
├─────────────────────────────┤
│  FOOTER  (links + copyright)│
└─────────────────────────────┘
```

---

## Important: Sections Stack Vertically by Default

`<section>` is a block element — it stacks vertically by default:

```
[  section: Hero      ]
[  section: Features  ]
[  section: CTA       ]
```

To place sections side by side, CSS flexbox is needed on the parent:
```css
/* CSS hint only — not HTML */
main { display: flex; flex-direction: row; }
```
