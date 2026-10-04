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
