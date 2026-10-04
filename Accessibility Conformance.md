# Accessibility conformance

Site files: `CSS Architecture Package/`. Open each page in a browser from that folder.

## Test scope

Four pages. Each one holds a check the others do not.

**Home** (`index.html`). Shared header, skip link, nav, `aria-current="page"`, footer, and heading outline. Two links use class `button`. One `video`, poster `images/video-placeholder.svg`, no `src`, and a `figcaption`.

**Services** (`services.html`). The only form: Name, Email (`aria-invalid="true"`, `aria-describedby="email-error"`), Area of interest, and "Submit request." The only table: caption, `th scope="col"`, and `data-label` on each cell. `print.css` targets this page.

**Media** (`media.html`). Squat setup links to `#player` with "Open video." One `video`, the same poster, no `src`, `aria-label`, and `aria-describedby="player-text"`. Locked cards have no link and no button. One `aside`.

**About** (`about.html`). The only `img` elements. Four figures, each with `alt`, `srcset`, and a `figcaption`. One `video`, the same poster, no `src`, and a `figcaption`. "YouTube technique library" is text. No YouTube URL is in the page.

Home, Services, and Media have no `img`. The photographs, alt text, and captions are on About.

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
