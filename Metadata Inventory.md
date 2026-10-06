# Metadata inventory

Site files: `CSS Architecture Package/`.

## 1. Page list

**Home** (`index.html`). Read the company name, then open tutorials or request a private online or in-home session.

**Media** (`media.html`). Watch the free beginner tutorials. Advanced clips stay labeled for members.

**Services** (`services.html`). Compare session types and prices, then request a session.

**About** (`about.html`). Read the trainer background, credentials, and platform list.

## 2. Title plan

**Home** (`index.html`). `<title>Home | Bulletproof Personal Training</title>`

**Media** (`media.html`). `<title>Media | Bulletproof Personal Training</title>`

**Services** (`services.html`). `<title>Services | Bulletproof Personal Training</title>`

**About** (`about.html`). `<title>About | Bulletproof Personal Training</title>`

## 3. Description plan

**Home** (`index.html`). `Bulletproof Personal Training: beginner and advanced technique videos plus private session requests.`

**Media** (`media.html`). `Free beginner tutorials and locked advanced training videos from Bulletproof Personal Training.`

**Services** (`services.html`). `Session types, pricing, and a request form for Bulletproof Personal Training.`

**About** (`about.html`). `Trainer background, credentials, and platform list for Bulletproof Personal Training.`

## 4. Heading and link check

**Home** (`index.html`). Heading: `Bulletproof Personal Training`. Links: `Watch tutorials` (`media.html`), `Request a session` (`services.html`).

**Media** (`media.html`). Heading: `Beginner tutorials`. Links: `Open video` (`#player`), `Back to tutorials` (`media.html`).

**Services** (`services.html`). Heading: `Services`. Links: `Request a session` (`#request`), `Media` (`media.html`).

**About** (`about.html`). Heading: `About the trainer`. Links: `Watch tutorials` (`media.html`), `Request a private session` (`services.html`).

## 5. Image context

**Home** (`index.html`). `images/video-placeholder.svg`. Poster on the highlight video. No `alt`. `aria-label` is `Highlight video placeholder`. The video is `aria-hidden="true"`. Caption: `Highlight video placeholder`. Nearby heading: `Bulletproof Personal Training`. Nearby text: `Learn beginner and advanced lifting technique from training videos, then request a private online or in-home session.`

**Media** (`media.html`). `images/video-placeholder.svg`. Poster on the squat setup player. No `alt`. `aria-label` is `Squat setup video placeholder`. The video is `aria-hidden="true"`. Nearby heading: `Player: Squat setup`. Nearby text: `Keep the whole foot on the floor, brace before you sit, and push through the heel on the way up.`

**About** (`about.html`). `images/video-placeholder.svg`. Poster on the trainer intro video. No `alt`. `aria-label` is `Trainer intro video placeholder`. The video is `aria-hidden="true"`. Caption: `Trainer intro video placeholder`. Nearby link: `Watch tutorials`. Nearby heading: `Coaching approach`.

**About** (`about.html`), under `Training spaces`.

- `images/home-gym-800.jpg`, with `images/home-gym-480.jpg` in `srcset`. `alt`: `Man in a gray shirt squatting with a loaded barbell in a garage.` Caption: `Home gym coaching`.
- `images/online-800.jpg`, with `images/online-480.jpg` in `srcset`. `alt`: `Open laptop on a wooden table beside a notebook, a pen, and a phone.` Caption: `Online sessions`.
- `images/small-space-800.jpg`, with `images/small-space-480.jpg` in `srcset`. `alt`: `Two adjustable dumbbells and loose plates on a gray floor.` Caption: `Small-space setup`.
- `images/notes-800.jpg`, with `images/notes-480.jpg` in `srcset`. `alt`: `Small blue spiral notepad next to a one-euro coin.` Caption: `Session notes`.

**Services** (`services.html`). No `img`. No poster.

## 6. Social preview plan

**About** (`about.html`). Title: `About | Bulletproof Personal Training`. Description: `Trainer background, credentials, and platform list for Bulletproof Personal Training.` URL: `https://github.com/vandyparkes/capstone-project/blob/main/CSS Architecture Package/about.html`. Image: `images/home-gym-800.jpg`.

## 7. Validation plan

Check each page in `CSS Architecture Package/`.

- One `<title>` per page, and it matches section 2.
- One `meta name="description"` per page, and it matches section 3.
- The heading named in section 4 is on that page. The two links named there use those `href` values.
- The four About `img` elements use the `alt` text in section 5. Each poster named there has no `alt`. Each video `aria-label` matches section 5.
- The About title, description, and `images/home-gym-800.jpg` match section 6.
- None of the four pages has `script type="application/ld+json"` or `schema.org` markup. Record that.
