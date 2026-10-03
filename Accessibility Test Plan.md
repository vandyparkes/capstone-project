# Accessibility test plan

Site files: `CSS Architecture Package/`. Open each page in a browser from that folder.

This plan lists checks. It does not record results.

## Pages to test

**Home** (`index.html`). This is the entry page. The skip link, header, main nav, and footer are the same pattern on every page. Home is where that pattern gets checked first, with `aria-current="page"` on Home. The page also has two links styled as buttons (`Watch tutorials`, `Request a session`), a `video` with `controls` and a poster and no `src`, and card links into Media, Services, and About.

**Services** (`services.html`). This is the only page with a form and the only page with a table. The form has required name, email, and area of interest, a submit button, and an email field already marked `aria-invalid="true"` with `aria-describedby="email-error"`. The pricing table has a caption and column headers. An in-page link goes to `#request`. `print.css` is for this page.

**Media** (`media.html`). This page holds the tutorial list and the player. Three beginner cards each link to `#player` with the text "Open video." The player is a `video` with `controls`, a poster, no `src`, `aria-label`, and `aria-describedby="player-text"`. Locked tutorials are text in cards. They are not buttons. A callout sits in an `aside`.

## Structure checks

On each page, view the source and the browser accessibility tree. Record the element, its accessible name, and whether it matches the list below.

### Landmarks

Each page has `html lang="en"`, one `header`, one `nav` with `aria-label="Main"`, one `main id="main"`, and one `footer`. The skip link sits before the `header`. It is an `a` with `href="#main"` and the text "Skip to main content." It is not inside a landmark.

Media adds one `aside` with `aria-labelledby="risk-heading"`. Home and Services have no `aside`.

Sections that name a heading use `aria-labelledby` on the `section` or `aside`. Check that each id in `aria-labelledby` is the id on that section's heading. Home's first section points at `home-heading`. Services' first section has an `h1` and no `aria-labelledby`. Media's first section is the same.

### Headings

One `h1` per page. No skipped levels. Compare the accessibility tree to this outline.

Home: `h1` Bulletproof Personal Training. `h2` What you can do here, with `h3` Watch technique and Request coaching. `h2` Start with these pages, with `h3` Media, Services, and About. `h2` Client notes. That last section has no content under the heading. Record what the tree shows there.

Services: `h1` Services. `h2` Session types, with `h3` Online technique, In-home training, and Advanced review. `h2` Pricing. `h2` Request a session.

Media: `h1` Media. `h2` Beginner tutorials, with `h3` Squat setup, Hinge pattern, and Push-up path. `h2` Advanced and locked tutorials, with `h3` Paused squat loading, Single-leg hinge, and Press variations. `h2` Training note. `h2` Player: Squat setup.

### Page titles

Read the tab title and the `title` element.

- Home: `Home | Bulletproof Personal Training`
- Services: `Services | Bulletproof Personal Training`
- Media: `Media | Bulletproof Personal Training`

Each title names the page, then the site. The `h1` is "Bulletproof Personal Training" on Home, "Services" on Services, and "Media" on Media.

### Links

Shared on every page: "Skip to main content" (`#main`), "Bulletproof PT" (`index.html`), and the nav items Home (`index.html`), Media (`media.html`), Services (`services.html`), and About (`about.html`).

`aria-current="page"` is on one nav link only. Home on Home, Services on Services, Media on Media. The other nav links do not have it.

Home also has "Watch tutorials" (`media.html`, class `button`), "Request a session" (`services.html`, class `button button--secondary`), a second "Watch tutorials" inside the `video`, "Open Media," "Open Services," "Open About," and a footer "Services" link.

Services also has "Request a session" (`#request`, class `button`) and a footer "Media" link.

Media also has three "Open video" links (`#player`), "Back to tutorials" (`media.html`) above the player, the same text inside the `video`, and a footer "Services" link.

For each link, record the visible text and the `href`. The three "Open video" links share the same `href` and the same text. Record that they point at one player whose heading is "Player: Squat setup."

### Buttons

Count `button` elements. Home has none. Media has none. Services has one: "Submit request," `type="submit"`.

Links with class `button` stay `a` elements. They have no `role="button"`. Check "Watch tutorials," "Request a session" on Home, and "Request a session" on Services.

Locked Media cards and the badge spans (`Beginner`, `Free`, `Advanced`, `Members only`) have no link and no button.

### Native HTML

Nav items and cards are `ul` and `li`. Prices are a `table` with `caption`, `thead`, `th scope="col"`, and `td`. The caption text is "Session type, access, price, and notes" and the caption has class `visually-hidden`.

The request form uses `form`, `label for`, `input`, `select`, and `button`. Name is `input type="text"`. Email is `input type="email"`. Area of interest is a `select` whose first `option` is "Choose one."

Players are `video` elements with `controls`. They are not a scripted control set. Home's accessible name is "Highlight video placeholder." Media's is "Squat setup video placeholder," described by `player-text`.

## Keyboard checks

Use the keyboard only. Load the page, click the address bar once, then Tab forward and Shift+Tab back. There is no `tabindex` and no script. Record each stop in order. Compare it to the source order below.

### Focus order

Shared start on every page: "Skip to main content," then "Bulletproof PT," then Home, Media, Services, About.

Home continues: "Watch tutorials," "Request a session," the `video` ("Highlight video placeholder"), "Open Media," "Open Services," "Open About," footer "Services." The `video` contains another "Watch tutorials" link. Record whether that inner link takes a stop. Cards without links do not get a stop.

Services continues: "Request a session" (`#request`), Name, Email, Area of interest, "Submit request," footer "Media."

Media continues: "Open video" under Squat setup, "Open video" under Hinge pattern, "Open video" under Push-up path, "Back to tutorials," the `video` ("Squat setup video placeholder"), footer "Services." The `video` contains another "Back to tutorials" link. Record whether that inner link takes a stop. Locked cards have no link and no button. Record that Tab moves from "Push-up path" to "Back to tutorials" without stopping on Paused squat loading, Single-leg hinge, or Press variations.

### Visible focus

`base.css` sets `:focus-visible` to a 3px solid outline, color `#9b1c1c`, offset 3px. On each stop, record whether that outline is visible on the control, including the skip link, nav links, button-styled links, the `video`, text links, and the Services fields and "Submit request."

The skip link is clipped to 1px until `:focus` (`.skip-link` in `components.css`). On the first Tab, record whether "Skip to main content" is on screen. Tab again and record whether it clips away.

### Skip link

The skip link is on Home, Services, and Media. From the first Tab, press Enter. Record where focus is after Enter, then Tab once more and record the next stop.

On Home the next controls in source after `#main` are "Watch tutorials," then "Request a session." On Services they are "Request a session" (`#request`), then Name. On Media they are the first "Open video," then the next "Open video."

On Services, press Enter on "Request a session" (`#request`). Record whether focus stays on that link or moves, and whether the next Tab reaches Name.

### Current page

`aria-current="page"` is on Home in the Home nav, Services in the Services nav, and Media in the Media nav. Tab to that link. Record the accessible state and the visible style from `states.css`: accent color `#9b1c1c` and an underline. Tab to the other three nav links and record that they do not expose current page.

### Traps

No page has a script. From the last stop (the footer link), Shift+Tab should walk back through the same stops. From the first stop, Shift+Tab should leave the page.

On each `video`, focus it, press Space, then Tab and Shift+Tab. Record whether focus can leave the `video`. There is no `src`.

On Services, focus Area of interest. Open it with the keyboard, change the option with the arrow keys, press Escape, then Tab. Record whether focus reaches "Submit request" and does not stay inside the `select`.

