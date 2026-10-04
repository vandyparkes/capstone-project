# Accessibility test plan

Site files: `CSS Architecture Package/`. Open each page in a browser from that folder.

## Pages to test

**Home** (`index.html`). Skip link, header, nav, footer, and `aria-current="page"` on Home. Links with class `button`: "Watch tutorials" (`media.html`), "Request a session" (`services.html`). `video` with `controls`, poster `images/video-placeholder.svg`, no `src`. Card links: "Open Media," "Open Services," "Open About."

**Services** (`services.html`). Form fields: Name, Email (`aria-invalid="true"`, `aria-describedby="email-error"`), Area of interest, "Submit request." Pricing table with a caption and column headers. Link "Request a session" (`#request`). Print styles in `print.css`.

**Media** (`media.html`). Three "Open video" links to `#player`. `video` with `controls`, poster `images/video-placeholder.svg`, no `src`, `aria-label`, `aria-describedby="player-text"`. Locked cards have no link and no button. Callout in an `aside`.

## Structure checks

On each page, view the source and the browser accessibility tree. Record the element and its accessible name.

### Landmarks

Each page: `html lang="en"`, one `header`, one `nav` with `aria-label="Main"`, one `main id="main"`, one `footer`. Skip link before the `header`: `a`, `href="#main"`, text "Skip to main content."

Media: one `aside` with `aria-labelledby="risk-heading"`. Home and Services: no `aside`.

For each `aria-labelledby`, record the id and the heading that uses that id. Home's first section uses `home-heading`. Services' first section has an `h1` and no `aria-labelledby`. Media's first section is the same.

### Headings

Record the heading outline.

Home: `h1` Bulletproof Personal Training. `h2` What you can do here. `h3` Watch technique. `h3` Request coaching. `h2` Start with these pages. `h3` Media. `h3` Services. `h3` About. `h2` Client notes. Record what is under "Client notes."

Services: `h1` Services. `h2` Session types. `h3` Online technique. `h3` In-home training. `h3` Advanced review. `h2` Pricing. `h2` Request a session.

Media: `h1` Media. `h2` Beginner tutorials. `h3` Squat setup. `h3` Hinge pattern. `h3` Push-up path. `h2` Advanced and locked tutorials. `h3` Paused squat loading. `h3` Single-leg hinge. `h3` Press variations. `h2` Training note. `h2` Player: Squat setup.

### Page titles

Record the tab title and the `title` element.

- Home: `Home | Bulletproof Personal Training`
- Services: `Services | Bulletproof Personal Training`
- Media: `Media | Bulletproof Personal Training`

Record the `h1` next to the title. Home `h1`: "Bulletproof Personal Training." Services `h1`: "Services." Media `h1`: "Media."

### Links

On every page, record text and `href`: "Skip to main content" (`#main`), "Bulletproof PT" (`index.html`), Home (`index.html`), Media (`media.html`), Services (`services.html`), About (`about.html`).

Record which nav link has `aria-current="page"`. Home on Home. Services on Services. Media on Media.

Home: "Watch tutorials" (`media.html`, class `button`), "Request a session" (`services.html`, class `button button--secondary`), "Watch tutorials" inside the `video`, "Open Media," "Open Services," "Open About," footer "Services."

Services: "Request a session" (`#request`, class `button`), footer "Media."

Media: "Open video" (`#player`) under Squat setup, Hinge pattern, and Push-up path. "Back to tutorials" (`media.html`) above the player. "Back to tutorials" inside the `video`. Footer "Services."

Record the text and `href` of the three "Open video" links and the player heading "Player: Squat setup."

### Buttons

Count `button` elements. Home: none. Media: none. Services: "Submit request," `type="submit"`.

Record the tag of "Watch tutorials," Home "Request a session," and Services "Request a session." Record any `role` on those links.

Record any link or button inside the locked Media cards and on the spans "Beginner," "Free," "Advanced," and "Members only."

### Native HTML

Record the tags for the nav list, the card lists, the pricing table (`caption`, `thead`, `th`, `td`), and the form (`label`, `input`, `select`, `button`).

Caption text: "Session type, access, price, and notes." Caption class: `visually-hidden`. Name: `input type="text"`. Email: `input type="email"`. Area of interest: `select`, first option "Choose one."

Record the tag and accessible name of each player. Home: "Highlight video placeholder." Media: "Squat setup video placeholder," `aria-describedby="player-text"`.

## Keyboard checks

Keyboard only. Click the address bar, then Tab and Shift+Tab. Record each stop. Record any `tabindex` in the source.

### Focus order

Every page starts: "Skip to main content," "Bulletproof PT," Home, Media, Services, About.

Home: "Watch tutorials," "Request a session," the `video` ("Highlight video placeholder"), "Open Media," "Open Services," "Open About," footer "Services." Record whether the "Watch tutorials" link inside the `video` takes a stop. Record any stop on a card that has no link.

Services: "Request a session" (`#request`), Name, Email, Area of interest, "Submit request," footer "Media."

Media: "Open video" (Squat setup), "Open video" (Hinge pattern), "Open video" (Push-up path), "Back to tutorials," the `video` ("Squat setup video placeholder"), footer "Services." Record whether the "Back to tutorials" link inside the `video` takes a stop. Record any stop on Paused squat loading, Single-leg hinge, or Press variations.

### Visible focus

On each stop, record the outline width, style, color, and offset. `base.css` `:focus-visible` is 3px solid `#9b1c1c`, offset 3px. Include the skip link, nav links, links with class `button`, each `video`, text links, the Services fields, and "Submit request."

First Tab: record whether "Skip to main content" is on screen. Next Tab: record whether it is clipped. `.skip-link` is 1px until `:focus`.

### Skip link

On Home, Services, and Media: Tab to "Skip to main content," press Enter, record where focus is, then Tab once and record the next stop.

Source order after `#main`: Home "Watch tutorials," then "Request a session." Services "Request a session" (`#request`), then Name. Media first "Open video," then the next "Open video."

Services: Enter on "Request a session" (`#request`). Record where focus is. Tab once. Record whether the next stop is Name.

### Current page

Tab to the nav link with `aria-current="page"`. Record the accessible state, the color, and the underline. `states.css` sets that link to `#9b1c1c` and underline. Tab to the other three nav links and record the current-page state on each.

### Traps

From the footer link, Shift+Tab back through the stops. From "Skip to main content," Shift+Tab once and record where focus goes.

On each `video`: focus it, press Space, Tab, and Shift+Tab. Record whether focus leaves the `video`.

Services: focus Area of interest, open it, press the arrow keys, press Escape, then Tab. Record whether the next stop is "Submit request."

## Visual checks

Chrome. Home, Services, and Media.

### Zoom and reflow

Viewports: 320px, 375px, 768px, 1280px. Then a 1280px window at 200% zoom and at 400% zoom. At each size, record sideways scroll on the document.

Record:

- Header: logo and Home, Media, Services, About on one row or wrapped.
- Home: "Watch tutorials" and "Request a session" stacked or on one row. Video frame ratio. The frame is `.media-object__frame` (16:9).
- Cards across: Home "What you can do here" (`.grid--2`, `minmax(18rem, 1fr)`). Home "Start with these pages," Media tutorial lists, and Services "Session types" (`.grid--3`, `minmax(16rem, 1fr)`).
- Media badges: "Beginner" with "Free," and "Advanced" with "Members only," on one row or stacked. Player frame ratio. Player section max: 54rem (`.container--media`).
- Services form: Name, Email, "Enter an email we can reply to, not only a colored border," and Area of interest inside the form. Form max: 32rem. Fields: `inline-size: 100%`.
- Services pricing. Content box: `min(100% - 2rem, 70rem)`. Under 48rem the rows stack and each cell shows its `data-label` (`@container (width < 48rem)`). 320px, 375px, 768px, 200% zoom, and 400% zoom are under 48rem. Record Type, Access, Price, and Notes on each row, including "Travel radius confirmed by email" and "Locked tutorials stay labeled until the rate is published." At 1280px the box is 70rem. Record whether the header cells show and the four values sit in columns.

At every width, record whether these lines stay fully on screen: "Bulletproof Personal Training," "Advanced and locked tutorials," "Enter an email we can reply to, not only a colored border."

### Text spacing

At 1280px and at 320px, apply this in DevTools:

```css
* {
  line-height: 1.5 !important;
  letter-spacing: 0.12em !important;
  word-spacing: 0.16em !important;
}
p {
  margin-bottom: 2em !important;
}
```

Record clipped text, overlap, and sideways scroll on the header, the three lines above, the Home button links, the Media badges, the Media callout, the Services table, and the email error. Remove the style after.

### Contrast

Record the computed foreground and background:

- `#1b1b1b` on `#f5f3ef` (page text, price table header cells)
- `#1b1b1b` on `#ffffff` (cards, form, price table body cells)
- `#5a5a5a` on `#f5f3ef` (footer)
- `#5a5a5a` on `#ffffff` (Media durations, stacked price labels)
- `#9b1c1c` on `#f5f3ef` (links, current nav item)
- `#9b1c1c` on `#ffffff` (links on cards, secondary button, focused skip link)
- `#ffffff` on `#9b1c1c` (primary button, Free badge)
- `#ffffff` on `#0d5c46` (Beginner)
- `#ffffff` on `#163a5f` (Advanced)
- `#ffffff` on `#5a5a5a` (Members only)
- `#7a4500` on `#ffffff` (email error, "Rate TBD")
- Focus outline `#9b1c1c` on `#f5f3ef` and on `#ffffff`

### Line length

At 1280px, record the used width of the Home intro, the Media intro, the Services intro, the Media callout, and the sentence under the player. Those paragraphs use `max-inline-size: 65ch`.

Record whether these wrap inside the content box: "Bulletproof Personal Training," "Advanced and locked tutorials," "Player: Squat setup."

### Print

Services print preview. Record the skip link, nav, buttons, form, pricing rows, session-type cards, and prices. `print.css` hides `.skip-link`, `nav`, `.button`, `.session-form`, and `.no-print`, and stacks the price rows.

Home and Media print preview. Record the video frame. `print.css` hides `.media-object__frame`.

## Complex content checks

Home, Services, and Media. Record what is in the source and what the page does.

### Form

Services only. `form.session-form`, `action="#"`, `method="post"`.

Record each `label for` against the field `id`:

- `name`: "Name (required)," `input type="text"`, `autocomplete="name"`, `required`
- `email`: "Email (required)," `input type="email"`, `autocomplete="email"`, `required`, `aria-invalid="true"`, `aria-describedby="email-error"`, `value="not-an-email"`
- `interest`: "Area of interest (required)," `select` `required`, first option "Choose one," then Online technique, In-home training, Advanced review

Record the text of `#email-error`: "Enter an email we can reply to, not only a colored border." The email field is inside `.field.is-invalid`. Record whether that sentence is on screen when the page loads.

"Submit request" is `button type="submit"`.

Leave the fields as loaded and press "Submit request." Record the browser message and which field is focused.

Fill Name. Leave Email as `not-an-email`. Leave Area of interest on "Choose one." Submit. Record the message and the focused field.

Set Email to `name@example.com`. Leave Area of interest on "Choose one." Submit. Record the message and the focused field.

Set Area of interest to "Online technique." Submit. Record whether the page stays on Services.

### Table

Services only. `table.price-table`.

Record the caption text "Session type, access, price, and notes" and that the caption has class `visually-hidden`. In the accessibility tree, record the caption and the column headers Type, Access, Price, Notes. Each `th` has `scope="col"`.

Record the three rows:

- Online technique, Video, $65, 45 minutes
- In-home training, In-person, $90, Travel radius confirmed by email
- Advanced video library, Members, Rate TBD, Locked tutorials stay labeled until the rate is published

"Rate TBD" is `td.is-tbd`. Each `td` has a `data-label` that matches its column name.

### Images

Home, Services, and Media have no `img`. Record that.

### SVGs

No inline `svg` on these pages. Home and Media use `images/video-placeholder.svg` as the `video` `poster`. The file is 1600 by 900, one `rect` with `fill="#d4d0c8"`, and `aria-hidden="true"` on the `svg`. Services does not use that file.

### Audio, video, and embeds

No `audio`. No `iframe`. No `track`. No `source`.

Home `video`: `controls`, `poster="images/video-placeholder.svg"`, no `src`, `aria-label="Highlight video placeholder"`. Inside the `video`: "Watch tutorials" (`media.html`). Record the controls on screen and the time shown.

Media `video`: `controls`, same poster, no `src`, `aria-label="Squat setup video placeholder"`, `aria-describedby="player-text"`. Inside the `video`: "Back to tutorials" (`media.html`). Under the player, `#player-text`: "Keep the whole foot on the floor, brace before you sit, and push through the heel on the way up." Record the controls on screen and the time shown.

Media cards show 8:12, 6:40, and 5:05 in `p.text-caption`. Those lines are not a `track`. The three "Open video" links use `href="#player"`. The player heading stays "Player: Squat setup."

Locked cards Paused squat loading, Single-leg hinge, and Press variations have no `video` and no control.

### Motion

Neither `video` has `autoplay`. Record whether anything plays on load.

`states.css`: `.button:active` and `.nav-list a:active` use `transform: translateY(1px)`. Inside `@media (prefers-reduced-motion: reduce)` that `transform` is `none`.

Turn on `prefers-reduced-motion: reduce`. Press a button-styled link and a nav link. Record the shift. Turn the preference off. Press the same controls. Record the shift.

## Tool plan

### Automated

Chrome. axe DevTools. Open `index.html`, `services.html`, and `media.html`. On each page run a full-page scan. Record the page, each rule id, the description, and the element. Record the scan output only.

### Manual

1. Keyboard on all three pages. Click the address bar, then Tab through every stop in the Keyboard checks section. Record the order, the 3px `#9b1c1c` outline, Enter on "Skip to main content," and the nav link with `aria-current="page"`. On each `video`, press Space, then Tab away.

2. Reflow at 320px CSS width on all three pages. Record sideways scroll, header wrap, card columns, and the Services price rows (Type, Access, Price, Notes from `data-label`). Repeat at 1280px and record the pricing header cells.

3. Services form and table. In the accessibility tree, record the caption "Session type, access, price, and notes," the column headers, and `#email-error` on the email field. Press "Submit request" with the fields as loaded. Record the browser message and the focused field. Then run the later submits in the Form section and record each message and focused field.

## Evidence plan

Write results in `Accessibility Conformance.md`. This plan stays the checklist. That file holds what the checks showed.

### Findings

One entry per finding. Number them in order, starting at F1.

Each entry records:

- Date, browser, and page (`index.html`, `services.html`, or `media.html`)
- The check name from this plan
- The steps run, including viewport width, zoom, or axe when those were used
- What showed up, quoted from the page or the axe rule id
- The element: tag, accessible name, and `id` or class when it has one

A check that matches the plan still gets a line: page, check name, and "matches the plan." axe output is pasted per page. No conformance line.

### Fixes

Under the finding number, record the file changed and the line that changed. Quote the text before and after. Leave the finding entry in place.

### Retests

Repeat the same steps on the same page, in the same browser, at the same width or zoom. Add R1 under that finding: date, steps, and what showed up after the change. If it still fails, add the next fix under the same number and retest again.

### Remaining limitations

End the evidence file with a limitations list. Each item names the page, what was not changed, and which check still shows it.

Include an item when a check cannot be finished from the files as they are: a `video` with no `src`, no `track`, and no transcript; About is not one of the three pages in this plan; an axe scan does not replace the manual checks. Do not mark those items fixed.


