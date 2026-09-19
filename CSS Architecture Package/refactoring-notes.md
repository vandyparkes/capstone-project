# Refactoring evidence

Before vs after for the CSS rewrite. The old version was one file with repeated hex values and long selectors. The files in `css/` are the rewrite.

## 1. Repeated values → tokens

**Before**

```css
.site-header nav ul li a {
  color: #9b1c1c;
}

.button {
  background: #9b1c1c;
  padding: 13px 22px;
}

.card {
  padding: 20px;
  border-radius: 7px;
}

input:focus {
  outline: 2px solid #9b1c1c;
}
```

**After**

Accent, spacing, radius, and focus live on `:root`. Buttons, current nav, and focus all use `--color-accent`. Card padding uses `--space-24`. Changing the accent token updates CTA, current page, and focus together.

## 2. High specificity → layers and short classes

**Before**

```css
header nav ul li a:hover {
  color: #9b1c1c;
}

main section div.card h3 {
  margin-bottom: 8px;
}
```

Those selectors are hard to override later.

**After**

```css
.nav-list a:hover { text-decoration: underline; }
.card { gap: var(--card-gap); }
```

Source order is reset → base → layout → components → utilities → states → overrides. No IDs. No `!important` on screen styles.

## 3. One-off tiles → one card pattern

**Before**

Home teasers, Media tutorials, and Services session types each had their own padding, border, and heading size. Locked tiles used `button[disabled]`, which looked unlockable.

**After**

One `.card` class. Badges carry Beginner / Advanced / Free / Locked. Locked tutorials use `.is-locked` plus copy, not a disabled button.

## 4. Unclear names → job names

**Before:** `.box1`, `.redtext`, `.bigpad`, `.linkon`

**After:** `.callout`, `.text-muted`, `.button`, `.nav-list a[aria-current="page"]`

## 5. Print afterthought → Services print sheet

**Before:** the pricing table clipped in landscape and nav still printed.

**After:** `css/print.css` hides nav, CTAs, the form, and embeds. Session cards and the table print in black and white, with stacked rows so prices stay attached to each session type.
