# 06 — CSS Flexbox (Complementary Hint)

> ⚠️ This is a CSS concept, not HTML. It is included here only because flexbox is essential to understand **why** some HTML layouts look horizontal even though block elements default to vertical stacking.

---

## Why Flexbox Matters for HTML Layout

By default, all block elements stack **vertically**:
```
[  div  ]
[  div  ]
[  div  ]
```

Flexbox lets you arrange them **horizontally** — or control spacing, alignment, and sizing — without changing the HTML structure at all.

---

## How to Activate Flexbox

You add it to the **parent** element in CSS:

```css
.container {
  display: flex;
}
```

Now all **direct children** of `.container` line up horizontally by default.

---

## The Mental Model

```
PARENT (flex container)  ← you set flex rules here
├── CHILD 1 (flex item)
├── CHILD 2 (flex item)
└── CHILD 3 (flex item)
```

---

## Most Important Properties

### On the Parent:

| Property | What it does | Common values |
|---|---|---|
| `flex-direction` | Row or column? | `row`, `column` |
| `justify-content` | Space along main axis | `flex-start`, `center`, `space-between` |
| `align-items` | Space along cross axis | `flex-start`, `center`, `stretch` |
| `gap` | Space between items | `10px`, `1rem` |
| `flex-wrap` | Wrap to next line? | `wrap`, `nowrap` |

### On the Child:

| Property | What it does |
|---|---|
| `flex: 1` | Grow to fill space equally |
| `flex: 0 0 200px` | Fixed size, no grow/shrink |

---

## The Two Axes

```
flex-direction: row →

Main axis:   →→→→→→→→→→→  (justify-content controls this)
Cross axis:  ↑↓            (align-items controls this)
```

When you switch to `flex-direction: column`, the axes flip.

---

## Common Layout Patterns

**Side by side:**
```css
.container { display: flex; flex-direction: row; gap: 16px; }
```
```
[ Item 1 ] [ Item 2 ] [ Item 3 ]
```

**Centered:**
```css
.container { display: flex; justify-content: center; align-items: center; }
```
```
|          [ Item ]          |
```

**Classic page layout:**
```css
.page    { display: flex; flex-direction: column; }
.content { display: flex; flex-direction: row; }
```
```
[ Header                    ]
[ Sidebar ] [ Main Content  ]
[ Footer                    ]
```

---

## Key Takeaway for HTML Learners

> If you see two block elements sitting side by side in a layout, flexbox (CSS) is always responsible — not HTML itself. HTML only controls **structure**. CSS controls **appearance and direction**.
