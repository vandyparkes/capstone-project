# Accessibility test plan

Site files: `CSS Architecture Package/`. Open each page in a browser from that folder.

This plan lists checks. It does not record results.

## Pages to test

**Home** (`index.html`). This is the entry page. The skip link, header, main nav, and footer are the same pattern on every page. Home is where that pattern gets checked first, with `aria-current="page"` on Home. The page also has two links styled as buttons (`Watch tutorials`, `Request a session`), a `video` with `controls` and a poster and no `src`, and card links into Media, Services, and About.

**Services** (`services.html`). This is the only page with a form and the only page with a table. The form has required name, email, and area of interest, a submit button, and an email field already marked `aria-invalid="true"` with `aria-describedby="email-error"`. The pricing table has a caption and column headers. An in-page link goes to `#request`. `print.css` is for this page.

**Media** (`media.html`). This page holds the tutorial list and the player. Three beginner cards each link to `#player` with the text "Open video." The player is a `video` with `controls`, a poster, no `src`, `aria-label`, and `aria-describedby="player-text"`. Locked tutorials are text in cards. They are not buttons. A callout sits in an `aside`.
