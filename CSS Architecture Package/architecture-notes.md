# Architecture notes

This is the first pass of production CSS for Bulletproof PT. Colors, type, and spacing can still change later by editing the tokens in `css/base.css`.

## Layer and order

`css/main.css` loads files in this order:

1. reset — box-sizing, zero body margin
2. base — tokens and default text
3. layout — header, footer, container, grids
4. components — nav, card, button, callout, form, table, media object, lists
5. utilities — small helpers that should win over components
6. states — hover, focus-visible, current page, invalid, locked
7. overrides — TBD price color

Later layers win, so I did not need long selectors like `header nav ul li a`. Print loads last and stays outside layers so it can override screen CSS. The only `!important` in print is for hiding nav/buttons that already set `display` earlier.

## Tokens

- One background, one card surface, one body text, one muted text, one accent, one warning.
- Beginner and Advanced have their own colors.
- One font, one body size, h1–h3, plus a smaller caption size for duration, prices, and badges.
- Spacing is 8 / 16 / 24 / 32 / 48.
- One radius and one border for cards, tables, and inputs.
- Focus uses `--focus-color`, `--focus-width`, and `--focus-offset`.
- `.card` sets `--card-padding` and `--card-gap`. `.session-form` sets `--form-gap`.

## Naming

Short names for what is on the page: `.card`, `.button`, `.callout`, `.price-table`. Variants are a second class (`.button--secondary`, `.badge--beginner`). States are `.is-locked` and `.is-invalid`. Current page uses `aria-current="page"`.

HTML uses `header`, `nav`, `main`, `section`, `aside`, `footer`, lists, `table`, and `form`. No `<article>`. Cards are list items.

## Browser checks

Checked around 375px and a wide window in Chrome:

- Nav wraps to a second line, no sideways overlap
- Video stacks above the bio on About; beside it when wide
- 2-up and 3-up cards on wide
- Skip link, nav, buttons, and form fields use the same 3px accent outline
- Invalid email on the Services form: warning border and error text
- Print preview on Services: nav, buttons, form, and media placeholders hide

Safari and Firefox still need a pass.
