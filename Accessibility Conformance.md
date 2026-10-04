# Accessibility conformance

Site files: `CSS Architecture Package/`. Open each page in a browser from that folder.

## Test scope

Four pages in `CSS Architecture Package/`. The media and typography inventory already listed the poster, the four photographs, the missing video files, and the missing captions and transcripts. Each page below is in the set because it holds a check the others do not.

**Home** (`index.html`). Shared skip link, header, nav, `aria-current="page"`, footer, and heading outline. Two links use class `button`. One `video`, poster `images/video-placeholder.svg`, no `src`, and a `figcaption`. The inventory recorded that poster as one gray rectangle, 1600 by 900.

**Services** (`services.html`). The only form and the only table. Name, Email (`aria-invalid="true"`, `aria-describedby="email-error"`), Area of interest, and "Submit request." Caption, `th scope="col"`, and `data-label` on each cell. `print.css` targets this page. No image and no video.

**Media** (`media.html`). The player and the locked cards. Squat setup links to `#player` with "Open video." One `video`, the same poster, no `src`, `aria-label`, and `aria-describedby="player-text"`. The inventory recorded no `track` and no transcript. Locked cards have no link and no button. One `aside`.

**About** (`about.html`). The only `img` elements. Four figures, each with `alt`, `srcset`, and a `figcaption`, matching the inventory. One `video`, the same poster, no `src`, and a `figcaption`. "YouTube technique library" is text. No YouTube URL is in the page.

## Semantic structure

Chrome. Home, Services, Media, and About.

### Page titles

- Home: `Home | Bulletproof Personal Training`. h1: Bulletproof Personal Training.
- Services: `Services | Bulletproof Personal Training`. h1: Services.
- Media: `Media | Bulletproof Personal Training`. h1: Media.
- About: `About | Bulletproof Personal Training`. h1: About the trainer.

### Landmarks

Each page: `html lang="en"`, skip link "Skip to main content" (`#main`), one `header`, one `nav` named "Main", one `main id="main"`, one `footer`.

`aria-current="page"` is on Home, Services, Media, or About for that page.

Named regions:

- Home: Bulletproof Personal Training, What you can do here, Start with these pages.
- Services: Session types, Pricing, Request a session.
- Media: Beginner tutorials, Advanced and locked tutorials, Player: Squat setup. The `aside` is complementary, name "Training note."
- About: Coaching approach, Beginner and advanced coaching, Other platforms, Training spaces.

### Headings

No level is skipped.

Home: h1 Bulletproof Personal Training. h2 What you can do here. h3 Watch technique. h3 Request coaching. h2 Start with these pages. h3 Media. h3 Services. h3 About.

Services: h1 Services. h2 Session types. h3 Online technique. h3 In-home training. h3 Advanced review. h2 Pricing. h2 Request a session.

Media: h1 Media. h2 Beginner tutorials. h3 Squat setup. h3 Hinge pattern. h3 Push-up path. h2 Advanced and locked tutorials. h3 Paused squat loading. h3 Single-leg hinge. h3 Press variations. h2 Training note. h2 Player: Squat setup.

About: h1 About the trainer. h2 Coaching approach. h3 Credentials. h2 Beginner and advanced coaching. h3 Foundations. h3 Loaded variations. h2 Other platforms. h2 Training spaces.

### Links and buttons

Home "Watch tutorials" and "Request a session" are `a` elements with class `button`. No `role`.

Services "Request a session" is an `a` to `#request`. "Submit request" is `button type="submit"`.

Home, Media, and About have no `button`. Services has one.

Locked cards have no link and no button. Beginner, Free, Advanced, and Members only are `span` text.

### Native HTML

Services form: `label for` on Name, Email, and Area of interest. Fields are `input`, `select`, and `button`. Names in the tree: "Name (required)," "Email (required)," "Area of interest (required)."

Services table name: "Session type, access, price, and notes." Headers: Type, Access, Price, Notes. Each `th` has `scope="col"`.

About: each photo is an `img` in a `figure` with a `figcaption`. The first image name is "Man in a gray shirt squatting with a loaded barbell in a garage." Its caption is "Home gym coaching." The other three use the same pattern.

Nav and the card groups are `ul`.

### Fixes

Home had a region named "Client notes." The only content was the h2. That section is gone.

Home, Media, and About each had a `video` with `controls` and no `src`. Chrome named the control "Unable to play media." The `aria-label` was not the name. `controls` is removed. The `video` has `aria-hidden="true"` and `tabindex="-1"`. The `aria-label` is still on the element.

Home `figcaption`: "Highlight video placeholder." About `figcaption`: "Trainer intro video placeholder." Media keeps the heading "Player: Squat setup" and the paragraph under the player.

About had a link "YouTube technique library" with `href="#"`. No YouTube URL is in the page. The list item is text. "Request a private session" still links to `services.html`.

Media had three links named "Open video," each `href="#player"`. The player heading is "Player: Squat setup." The Hinge pattern and Push-up path links are gone. Squat setup still links to `#player`.

`css/reset.css` sets `figure { margin: 0; }`.

### Retest

Home has no "Client notes" heading. The caption "Highlight video placeholder" is under the frame. The `video` is ignored in the accessibility tree. The control bar is gone.

Media has one "Open video" link, on Squat setup, `href="#player"`. Hinge pattern and Push-up path have no link. The player heading is still "Player: Squat setup."

About: "YouTube technique library" is not a link. The caption "Trainer intro video placeholder" is under the frame. The `video` has `aria-hidden="true"` and no `controls`.

Services was not edited. The title, landmarks, headings, form names, table name, and "Submit request" match the check above.

## Keyboard and focus

Chrome. Home, Services, Media, and About.

### Focus order

Each page starts: Skip to main content, Bulletproof PT, Home, Media, Services, About.

Home then: Watch tutorials, Request a session, Open Media, Open Services, Open About, footer Services.

Services then: Request a session, Name, Email, Area of interest, Submit request, footer Media.

Media then: Open video, Back to tutorials, footer Services. Hinge pattern, Push-up path, and the locked cards are not stops. The `video` `tabindex` is `-1`.

About then: Request a private session, footer Media. YouTube technique library is not a stop. The photos are not stops.

No `tabindex` above 0. No key script.

### Skip link

Enter on "Skip to main content" set the hash to `#main` and left focus on the body.

`main` now has `tabindex="-1"` on all four pages. After Enter, focus is on `main`. The next stop is the first control inside `main`: Watch tutorials on Home, Request a session on Services, Open video on Media, Request a private session on About.

### Focus visible

`:focus-visible` is 3px solid `#9b1c1c`, offset 3px.

The skip link on focus has a white background. "Skip to main content" was on screen with that outline.

The current nav link uses the same outline. On About the link text was underline, color `rgb(155, 28, 28)`. Home, Media, and Services used that color and underline. The other nav links were `rgb(27, 27, 27)` with no underline. The tree state was current.

After the skip link, `main` had the same 3px solid outline.

### Traps

Nothing keeps focus. The `video` is not a stop. Area of interest is a `select`. The stops run forward from the skip link and back from the footer link.

### Fix

`index.html`, `services.html`, `media.html`, and `about.html`: `tabindex="-1"` on `main`.

`.skip-link:focus` in `css/components.css` sets `overflow: visible`.

### Retest

On all four pages, the skip link moves focus to `main`. The outline on the skip link, the current nav link, and `main` is 3px solid `rgb(155, 28, 28)`, offset 3px.

## Zoom, reflow, text spacing, and contrast

Chrome. Home, Services, Media, and About.

Widths: 320, 375, 640, 768, and 1280 CSS pixels. 640 is a 1280 window at 200%. 320 is that window at 400%.

### Reflow

No sideways scroll at those widths.

Home at 320 and 375: the logo sits above Home, Media, Services, and About. "Bulletproof Personal Training" wraps. "Watch tutorials" and "Request a session" stack. The frame stays 16:9.

Home at 640, 768, and 1280: the nav is one row. The two button links are one row. At 1280 the intro is 674px wide.

Services at 320: price rows stack. The header row is clipped. The first cell shows the label "Type". The email error wraps and stays in the form. Fields stay inside the form.

Services at 1280: headers Type, Access, Price, and Notes show. The four values sit in columns. The intro is 674px wide.

Media at 320: "Advanced and locked tutorials" wraps to two lines. "Advanced" and "Members only" stack. The player frame stays 16:9. The callout stays inside the page.

Media at 1280: that heading is one line. "Advanced" and "Members only" share a row. The intro, the callout, and the sentence under the player are 674px wide. "Player: Squat setup" is one line.

About at 320: the video sits above the bio. The four photos stack. "YouTube technique library" stays inside the page.

About at 1280: the video sits beside the bio. The four photos sit in one row.

### Text spacing

At 320 and at 1280, on each page:

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

No sideways scroll. No clipped heading, link, paragraph, badge, table cell, or email error. The style was removed after the check.

### Contrast

Computed colors:

- `rgb(27, 27, 27)` on `rgb(245, 243, 239)`: 15.54. Page text and price header cells.
- `rgb(27, 27, 27)` on `rgb(255, 255, 255)`: 17.22. Cards, fields, and price body cells.
- `rgb(90, 90, 90)` on `rgb(245, 243, 239)`: 6.22. Footer text and figcaptions.
- `rgb(90, 90, 90)` on `rgb(255, 255, 255)`: 6.90. Durations and stacked price labels.
- `rgb(155, 28, 28)` on `rgb(245, 243, 239)`: 7.35. Links, the current nav item, and the focus outline.
- `rgb(155, 28, 28)` on `rgb(255, 255, 255)`: 8.15. Links on cards, the secondary button, and the focus outline on white.
- `rgb(255, 255, 255)` on `rgb(155, 28, 28)`: 8.15. Primary button and the Free badge.
- `rgb(255, 255, 255)` on `rgb(13, 92, 70)`: 7.97. Beginner.
- `rgb(255, 255, 255)` on `rgb(22, 58, 95)`: 11.64. Advanced.
- `rgb(255, 255, 255)` on `rgb(90, 90, 90)`: 6.90. Members only.
- `rgb(122, 69, 0)` on `rgb(255, 255, 255)`: 7.84. The email error and "Rate TBD".

### Fix

The field border was `#d4d0c8` on white. That pair is 1.54. The same border on the page background is 1.39.

`--color-border` in `css/base.css` is now `#8a877e`. On white that is 3.59. On `rgb(245, 243, 239)` that is 3.24.

### Retest

The Name field border is `rgb(138, 135, 126)`. The card border is the same. The invalid email border stays `rgb(122, 69, 0)`.

Services at 320 still has no sideways scroll. The email error stays inside the form.

## Forms and tables

Chrome. Services (`services.html`). Home, Media, and About have no form and no table.

### Form

`form.session-form`, `action="#"`, `method="post"`.

`label for` matches `name`, `email`, and `interest`. Label text: "Name (required)", "Email (required)", "Area of interest (required)".

On load, at 1280:

- Name: required, not invalid. `#name-error` is `display: none`. Text: "Enter your name."
- Email: required, invalid. Value `not-an-email`. `aria-invalid="true"`, `aria-describedby="email-error"`. The error is on screen: "Enter an email we can reply to, not only a colored border."
- Area of interest: required, not invalid. Value "Choose one." `#interest-error` is `display: none`. Text: "Choose a session type."
- "Submit request" is `button type="submit"`.

Before the fix, the tree marked Area of interest invalid on load. The source had no `aria-invalid` on that select and no error text. Name and Area of interest errors were only the browser message.

### Fix

`services.html`. Name has `aria-describedby="name-error"` and the paragraph "Enter your name." Area of interest has `aria-invalid="false"`, `aria-describedby="interest-error"`, and the paragraph "Choose a session type." Both paragraphs use `field-error`, so they stay hidden until `.is-invalid`.

On `invalid`, the browser message is cancelled, the field gets `aria-invalid="true"` and `.is-invalid`, and focus moves to the first invalid field. A valid email, a filled name, or a chosen session type clears that state.

### Retest

Email set to `name@example.com`. Invalid cleared. The email error left the tree.

Submit with Name empty, that email, and Area of interest on "Choose one." Focus moved to Name. On screen: "Enter your name." and "Choose a session type." The email error stayed off. Name and Area of interest were invalid.

Name filled. "Enter your name." left the tree. Submit again. Focus moved to Area of interest. "Choose a session type." stayed on screen.

Area of interest set to "Online technique." That error left. The field was not invalid.

Submit with all three filled. The page left the form. URL `services.html#`. Title "Error response". Text: "Error code: 501" and "Unsupported method ('POST')." The form has no confirmation text.

### Table

`table.price-table`. Caption "Session type, access, price, and notes", class `visually-hidden`. The table name in the tree is that caption.

Column headers: Type, Access, Price, Notes. Each `th` has `scope="col"`.

Each body row starts with `th scope="row"`: Online technique, In-home training, Advanced video library. Each cell has a `data-label` that matches its column.

At 1280 the header row is on screen, height 57px. Rows are table rows. `::before` content is `none`. No sideways scroll.

At 320 the header row is clipped to 1px. Rows stack. The first cell shows "Type". The next shows "Access". No sideways scroll. `scrollWidth` and `clientWidth` were both 305. The tree still has the table name, the column headers, and the row headers. Cell names include the `data-label` text.

### Fix

Print at 1280 stacked the rows and showed Type, Access, Price, and Notes as their own block. The cells had no `data-label` text. `::before` content was `none`.

`print.css` now clips `thead` and sets `content: attr(data-label)` on `td::before` and `tbody th::before`.

### Retest

Print at 1280. The form is `display: none`. The header row is clipped, height 1px. Rows stack. "Type" is on the first cell and "Access" is on the next, both `rgb(0, 0, 0)`.

A filled submit still ends on the file server 501 page. Nothing in the form is sent.

## Media, motion, and alternatives

Chrome. Home, Media, and About. Services has no `img`, `video`, `audio`, `iframe`, `svg`, or `track`.

### Images

About only. Four `img` elements. The alt is not the figcaption.

- "Man in a gray shirt squatting with a loaded barbell in a garage." Figcaption: Home gym coaching.
- "Open laptop on a wooden table beside a notebook, a pen, and a phone." Figcaption: Online sessions.
- "Two adjustable dumbbells and loose plates on a gray floor." Figcaption: Small-space setup.
- "Small blue spiral notepad next to a one-euro coin." Figcaption: Session notes.

Those alts are the image names in the tree. The figcaptions are separate text. Home and Media have no `img`.

### SVG

No inline `svg`. Home, About, and Media use `images/video-placeholder.svg` as the `video` poster. The file is one `rect`, fill `#d4d0c8`, 1600 by 900. The `svg` has `aria-hidden="true"`. No `title`. No `desc`.

### Video, captions, transcripts, embeds

No `audio`. No `iframe`. No `track`. No `src`. `autoplay` is false. `paused` is true. `controls` is false.

Each `video` has `aria-hidden="true"` and `tabindex="-1"`. None of them is in the tree.

Home. Figcaption: "Highlight video placeholder." The link inside the `video`, "Watch tutorials" (`media.html`), has width 0. The same link above the frame is in the tree.

Media. Heading: "Player: Squat setup." `#player-text`: "Keep the whole foot on the floor, brace before you sit, and push through the heel on the way up." "Open video" is one link, `href="#player"`, width 313. "Back to tutorials" (`media.html`) sits above the player, width 114. The copy inside the `video` has width 0. The times 8:12, 6:40, and 5:05 are paragraphs. Paused squat loading, Single-leg hinge, and Press variations have no link and no button.

About. Figcaption: "Trainer intro video placeholder." "YouTube technique library" is text. No YouTube URL is in the page.

Print on Media. `.media-object__frame` is `display: none`. "Back to tutorials" stays `inline`. `#player-text` stays on screen, width 674.

### Fix

About. The only "Watch tutorials" link was inside the `video`. Width 0. It was not in the tree.

`about.html` adds `<p><a href="media.html">Watch tutorials</a></p>` after the figcaption. The link inside the `video` stays.

### Retest

The new link is in the tree, `href="media.html"`, width 105. The link inside the `video` is still width 0. The figcaption is still "Trainer intro video placeholder."

### Motion

No `@keyframes`. The shift is `.button:active` and `.nav-list a:active`, `translateY(1px)`.

With `prefers-reduced-motion: reduce` on, both computed transforms were `none`. With it off, both were `matrix(1, 0, 0, 1, 0, 1)`.

Home, About, and the Media player have no video file, no `track`, and no transcript. The poster does not show the lift. "YouTube technique library" is not a link.

## Automated and manual checks

Chrome. axe-core 4.10.3. Home, Services, Media, and About. Full-page scan. Incomplete was empty on each page.

### Automated

Home. 31 passes. One violation: `aria-hidden-focus`, serious. Help: "ARIA hidden element must not be focusable or contain focusable elements." Target: `video`. The link inside it is "Watch tutorials" (`media.html`).

Services. 43 passes. No violations.

Media. 32 passes. One violation: `aria-hidden-focus`, serious. Same help. Target: `video`. The link inside it is "Back to tutorials" (`media.html`).

About. 34 passes. One violation: `aria-hidden-focus`, serious. Same help. Target: `video`. The link inside it is "Watch tutorials" (`media.html`).

### Keyboard

Focusable controls in source order. No `tabindex` above 0.

Home: Skip to main content, Bulletproof PT, Home, Media, Services, About, Watch tutorials, Request a session, Watch tutorials inside the `video`, Open Media, Open Services, Open About, footer Services.

Media: Skip to main content, Bulletproof PT, Home, Media, Services, About, Open video, Back to tutorials, footer Services. The link inside the `video` was also a stop. Locked cards were not stops.

About: Skip to main content, Bulletproof PT, Home, Media, Services, About, Watch tutorials inside the `video`, Watch tutorials, Request a private session, footer Media.

Services: Skip to main content, Bulletproof PT, Home, Media, Services, About, Request a session, Name, Email, Area of interest, Submit request, footer Media.

`:focus-visible` uses `--focus-width` 3px, `--focus-color` `#9b1c1c`, `--focus-offset` 3px. `.skip-link:focus` removes the clip and sets the background to the surface color.

### Zoom and reflow

No sideways scroll at 320, 640, or 1280. 640 is a 1280 window at 200%.

Home at 320: the `h1` is 77px tall. The two button links are 88px tall. Home at 640: those links are 44px tall. The `h1` is 593px wide and does not overflow.

Media at 320: "Advanced and locked tutorials" is 58px tall. At 1280 it is 29px tall.

Services at 320: price rows are `display: block`. The header row is 1px tall. The next cell's label is "Access". At 1280 the rows are `table-row` and the header row is 57px tall.

About at 320: the first photo is 273px wide. The window content is 305px wide.

### Visual and semantic

Each page has one `header`, one `nav`, one `main`, and one `footer`. Media has one `aside`.

Home headings: h1 Bulletproof Personal Training. h2 What you can do here. h3 Watch technique. h3 Request coaching. h2 Start with these pages. h3 Media. h3 Services. h3 About.

About headings: h1 About the trainer. h2 Coaching approach. h3 Credentials. h2 Beginner and advanced coaching. h3 Foundations. h3 Loaded variations. h2 Other platforms. h2 Training spaces.

`aria-current="page"` is on the matching nav link. On Services that link is `rgb(155, 28, 28)`.

Computed pairs:

- `rgb(27, 27, 27)` on `rgb(245, 243, 239)`: 15.54.
- `rgb(155, 28, 28)` on `rgb(245, 243, 239)`: 7.35. The current nav link.
- `rgb(122, 69, 0)` on `rgb(255, 255, 255)`: 7.84. The email error on the form.

### Fix

The link inside each `video` was still in the tab order. The `video` is `aria-hidden="true"`.

`index.html`, `media.html`, and `about.html`: `tabindex="-1"` on that inner link. The visible links stay in the tab order.

### Retest

axe-core 4.10.3. No violations.

- Home: 32 passes. Stops no longer include the link inside the `video`.
- Services: 43 passes. Stops unchanged.
- Media: 33 passes. Stops: Open video, Back to tutorials, footer Services. The inner link `tabIndex` is -1.
- About: 35 passes. Stops: Watch tutorials, Request a private session, footer Media. The inner link `tabIndex` is -1.

## Accessibility tree sample

Chrome accessibility tree. Services (`services.html`) at 1280. 196 nodes.

### What was checked

Document name: `Services | Bulletproof Personal Training`.

Landmarks: `banner` with no name, `navigation` "Main", `main` with no name and focusable, `contentinfo` with no name. Regions: Session types, Pricing, Request a session.

Headings: h1 Services. h2 Session types. h3 Online technique. h3 In-home training. h3 Advanced review. h2 Pricing. h2 Request a session.

Links: Skip to main content, Bulletproof PT, Home, Media, Services, About, Request a session, footer Media. The page snapshot marks Services current. In the full tree, that link's properties are focusable and the URL `services.html`.

Form:

- Textbox "Name (required)". `required` true. `invalid` false. `describedby` `name-error`. "Enter your name." is not in the tree.
- Textbox "Email (required)". `required` true. `invalid` true. `describedby` `email-error`. The tree includes "Enter an email we can reply to, not only a colored border."
- Combobox "Area of interest (required)". `invalid` false. `hasPopup` menu. `expanded` false. `describedby` `interest-error`. Options: Choose one, Online technique, In-home training, Advanced review. The property list has no `required`. The page snapshot lists required.
- Button "Submit request".

Table name: "Session type, access, price, and notes." The caption node itself has no name. Column headers: Type, Access, Price, Notes. Row headers: Online technique, In-home training, Advanced video library. Cells: Video, $65, 45 minutes. In-person, $90, Travel radius confirmed by email. Members, Rate TBD, Locked tutorials stay labeled until the rate is published.

### Limits

This is the Chrome tree for one page at 1280. It is not speech, and it does not include Home, Media, or About.

At this width the cell names do not include the stacked `data-label` text.

"Enter your name." and "Choose a session type." are not in the tree. Those paragraphs stay `display: none` until the field is invalid.

The combobox property list does not set `required`. The word is in the label.

The full tree dump has no `current` property. The page snapshot does list current on Services.

`banner`, `main`, and `contentinfo` have no names.

## Remediation log

### F1

Issue. Enter on "Skip to main content" left focus on the body.

Evidence. Chrome. Home, Services, Media, and About. The hash became `#main`. Focus stayed on the body.

Impact. The next Tab did not start at the first control in `main`.

Priority. High.

Fix. `tabindex="-1"` on `main` in `index.html`, `services.html`, `media.html`, and `about.html`.

Retest. On all four pages, Enter moves focus to `main`. The next stop is Watch tutorials on Home, Request a session on Services, Open video on Media, and Request a private session on About.

### F2

Issue. The field border was `#d4d0c8` on white. That pair is 1.54. The same border on the page background is 1.39.

Evidence. Chrome. Services. Computed border color on the Name field.

Impact. The field edge is under 3:1.

Priority. High.

Fix. `--color-border` in `css/base.css` is `#8a877e`. On white that is 3.59. On `rgb(245, 243, 239)` that is 3.24.

Retest. The Name field border is `rgb(138, 135, 126)`. The card border is the same. The invalid email border stays `rgb(122, 69, 0)`.

### F3

Issue. Area of interest was invalid on load and had no error text. Name and Area of interest errors were only the browser message.

Evidence. Chrome accessibility tree on Services. The combobox was `invalid` true, with no `describedby` and no error text. Name was `invalid` false and had no error element.

Impact. The select was marked invalid before submit. A failed submit did not put a Name or Area of interest message in the page.

Priority. Medium.

Fix. `services.html`. Name has `#name-error`, "Enter your name." Area of interest has `aria-invalid="false"` and `#interest-error`, "Choose a session type." On `invalid`, the browser message is cancelled, the field is marked invalid, and focus moves to the first invalid field.

Retest. On load, Area of interest is required and not invalid. Email set to `name@example.com` cleared the email error. Submit with Name empty focused Name and showed "Enter your name." and "Choose a session type." After Name was filled, submit focused Area of interest. Choosing "Online technique" cleared that error.

### F4

Issue. Print at 1280 stacked the price rows. The cells had no column label.

Evidence. Chrome print emulation at 1280. `::before` content was `none`. The header row was a separate block: Type, Access, Price, Notes.

Impact. The printed values were not paired with those column names.

Priority. Medium.

Fix. `print.css` clips `thead` and sets `content: attr(data-label)` on `td::before` and `tbody th::before`.

Retest. Print at 1280. The header row is 1px tall. Rows stack. "Type" is on the first cell and "Access" is on the next, both `rgb(0, 0, 0)`. The form is `display: none`.

### F5

Issue. Each `video` is `aria-hidden="true"` and contained a link that was still a tab stop.

Evidence. axe-core 4.10.3. Rule `aria-hidden-focus`, serious, on Home, Media, and About. Target: `video`. Home's stop list included "Watch tutorials" inside the `video`.

Impact. Tab reached a link that was not in the accessibility tree.

Priority. High.

Fix. `tabindex="-1"` on the link inside the `video` in `index.html`, `media.html`, and `about.html`. The visible links stay in the tab order.

Retest. axe-core 4.10.3. No violations. Home 32 passes, Services 43, Media 33, About 35. Those inner links are not in the stop lists. Each inner `tabIndex` is -1.

### F6

Issue. About's only "Watch tutorials" link was inside the `video`.

Evidence. Chrome. The link's width was 0. It was not in the accessibility tree. The figcaption was "Trainer intro video placeholder."

Impact. That link was not on screen and not in the tree.

Priority. Medium.

Fix. `about.html` adds `<p><a href="media.html">Watch tutorials</a></p>` after the figcaption. The link inside the `video` stays.

Retest. The new link is in the tree, `href="media.html"`, width 105. The link inside the `video` is still width 0. The figcaption is unchanged.

## Conformance summary

Chrome. Home, Services, Media, and About.

### What appears to conform

Each page has one title, one `h1`, one `header`, one `nav` named "Main", one `main`, and one `footer`. Heading levels are not skipped. `aria-current="page"` is on the matching nav link. The page snapshot lists that link as current.

The skip link moves focus to `main`. The next stop is the first control in `main`. No `tabindex` is above 0. The focus ring is 3px solid `#9b1c1c`, offset 3px.

No sideways scroll at 320, 640, or 1280. Text spacing at 320 and 1280 did not clip text. The recorded text pairs are 6.22 or higher. The field border on white is 3.59.

Services labels match Name, Email, and Area of interest. Email loads invalid with its error text. The table name is "Session type, access, price, and notes." Column headers have `scope="col"`. Each body row starts with `scope="row"`.

About's four image names match the alts. The figcaptions are separate. The poster SVG is `aria-hidden="true"`. Nothing autoplays. With reduced motion on, the press shift is `none`.

axe-core 4.10.3 reported no violations after F5. Home 32 passes, Services 43, Media 33, About 35.

### What was fixed

F1. `tabindex="-1"` on `main`.

F2. `--color-border` is `#8a877e`.

F3. Name and Area of interest have error text in the page. Area of interest is not invalid on load.

F4. Print puts the column label on each stacked price cell.

F5. The link inside each `video` has `tabindex="-1"`.

F6. About has a visible "Watch tutorials" link under the figcaption.

Earlier edits: the empty "Client notes" section is gone. The `video` elements have no `controls`. "YouTube technique library" is text. Media has one "Open video" link.

### What remains limited

Home, About, and the Media player have no video file, no `track`, and no transcript. The poster is one gray rectangle. "YouTube technique library" is not a link.

A filled submit leaves the form. The file server returns "Error code: 501" and "Unsupported method ('POST')." The form has no confirmation text.

The Services tree sample is one page at 1280. It is not speech. "Enter your name." and "Choose a session type." are absent until those fields are invalid. The combobox property list does not set `required`. The full tree dump has no `current` property. `banner`, `main`, and `contentinfo` have no names.

### Check again before release

Run a screen reader on Home, Media, and About, and on Services at 320. Read the current nav state, the combobox required state, and the stacked price cells.

Submit the form where POST is supported. Record the confirmation.

Add a video file only with the caption and transcript that belong to that file. Add a YouTube address only if one is available.

Run axe-core 4.10.3 again after those changes.
