# Media and Typography Inventory

Bulletproof Personal Training

## Images

Checked `index.html`, `about.html`, `media.html`, and `services.html`, and the files in `CSS Architecture Package/images/`.

### Video poster

![Solid gray rectangle, 1600 by 900](../CSS%20Architecture%20Package/images/video-placeholder.svg)

`CSS Architecture Package/images/video-placeholder.svg`

**Purpose**  
Poster for the highlight video on Home, the intro video on About, and the player on Media. All three use this file.

**Source**  
This file. The SVG does not name another source.

**License / permission**  
Not recorded.

**Original format**  
SVG

**Current format**  
SVG

**Current dimensions**  
1600 by 900. The `viewBox` is `0 0 1600 900`. The file is 148 bytes. It is one rectangle, fill `#d4d0c8`.

**Expected display size**  
The poster fills `.media-object__frame`. The frame is 16:9. The video is `inline-size: 100%`, `block-size: 100%`, and `object-fit: cover`. Home is capped by `.container` at `70rem`, which is 1120 by 630 at a 16px root. About uses the wider column of `.media-split` once the container is over `64rem`, recorded at 602 by 339. Media is capped by `.container--media` at `54rem`, recorded at 864 by 486. Narrower windows keep the same ratio at the container width.

### Card width screenshot

![Screenshot of two Squat setup cards, a narrow card with stacked badges and a wide card with badges on one row](../CSS%20Architecture%20Package/images/card-two-widths.png)

`CSS Architecture Package/images/card-two-widths.png`

**Purpose**  
Screenshot of the card at two widths. It is not used on Home, About, Media, or Services. `card-width-test.md` describes a 12rem box and a 28rem box and does not name this file.

**Source**  
The file metadata `UserComment` is Screenshot. No URL is stored in the file.

**License / permission**  
Not recorded.

**Original format**  
PNG

**Current format**  
PNG

**Current dimensions**  
812 by 393, 8-bit RGBA, 72 dpi, not interlaced. The file is 35,175 bytes.

**Expected display size**  
Not placed on Home, About, Media, or Services. The file is 812 by 393.

### Training space pictures

About lists four slots under Training spaces. Each slot is a `div` with `role="img"`. There is no `img` and no image file, so there is nothing to embed.

`planning-brief-starter/content-inventory-template.md` lists these as C7, Training Images. That row says the purpose is to support the brand and show training in action, the source/owner is Trainer, the status is Risky, and the note is "Confirm ownership, licensing, and alt text."

**License / permission**  
Not recorded.

**Original format**  
No file.

**Current format**  
No file. The slot is a box with `background: var(--color-border)`, which is `#d4d0c8`.

**Current dimensions**  
No file, so no pixel size.

**Expected display size**  
Each slot is at least `8rem` tall. The row is `.grid--4`, `repeat(auto-fill, minmax(14rem, 1fr))`, inside a container no wider than `70rem`. On a wide window that container is `70rem`, four tracks fit, and each slot is 16.75rem wide by 8rem tall (268 by 128 at a 16px root).

1. Home gym squat rack with a barbell. Figcaption on the page: Home gym coaching.
2. Laptop set up for an online training session. Figcaption on the page: Online sessions.
3. Dumbbells and a bench in a small training space. Figcaption on the page: Small-space setup.
4. Notebook with lift cues next to a water bottle. Figcaption on the page: Session notes.

Services has no image. The logo is the text "Bulletproof PT", not an image file.

## Alt text plan

### Video poster

**Type**  
Decorative

**Alt text**  
None. The file is a flat gray rectangle. It does not show the highlight, the trainer, or the squat.

**Alternative treatment**  
The poster is not an `img`, so it has no `alt`. Each `video` already has an `aria-label`. Home: "Highlight video placeholder." About: "Trainer intro video placeholder." Media: "Squat setup video placeholder."

### Card width screenshot

**Type**  
Informative

**Alt text**  
Bulletproof PT above two Squat setup cards. The narrow card stacks the Beginner and Free badges. The wide card puts those badges on one row. Both show 8:12, "Foot stance, brace, and a controlled descent.", and Open video.

### Training space pictures

**Type**  
Informative

**Alt text**  
No image file yet. The draft alt is the `aria-label` already on each slot. The figcaption stays on the figure and is not repeated in the alt. There is no file to compare this text to.

1. Alt: "Home gym squat rack with a barbell." Figcaption: Home gym coaching.
2. Alt: "Laptop set up for an online training session." Figcaption: Online sessions.
3. Alt: "Dumbbells and a bench in a small training space." Figcaption: Small-space setup.
4. Alt: "Notebook with lift cues next to a water bottle." Figcaption: Session notes.

## Media

Checked `index.html`, `about.html`, `media.html`, and `services.html`. No `audio`. No `iframe`. No video file.

### Home highlight video

**Caption**  
None.

**Transcript**  
None.

**Control**  
The `video` has `controls`. It has no `src`, no `source`, and no `track`.

**Motion**  
Nothing plays.

**Fallback**  
Poster is `images/video-placeholder.svg`. The `aria-label` is "Highlight video placeholder." Print CSS hides `.media-object__frame`.

**Privacy**  
No external media URL. The page does not load a third-party player.

### About intro video

**Caption**  
None.

**Transcript**  
None.

**Control**  
The `video` has `controls`. It has no `src`, no `source`, and no `track`.

**Motion**  
Nothing plays.

**Fallback**  
Poster is `images/video-placeholder.svg`. The `aria-label` is "Trainer intro video placeholder." Print CSS hides `.media-object__frame`.

**Privacy**  
No external media URL. The page does not load a third-party player.

### Media player

The heading is "Player: Squat setup." The text under the player is "Keep the whole foot on the floor, brace before you sit, and stand up without rushing the knees forward."

**Caption**  
None.

**Transcript**  
None.

**Control**  
The `video` has `controls`. It has no `src`, no `source`, and no `track`.

**Motion**  
Nothing plays.

**Fallback**  
Poster is `images/video-placeholder.svg`. The `aria-label` is "Squat setup video placeholder." Print CSS hides `.media-object__frame`.

**Privacy**  
No external media URL. The page does not load a third-party player.

### Tutorial cards

`planning-brief-starter/content-inventory-template.md` lists C6, Video Files and Explanations. That row says the source/owner is Trainer, the status is Risky, and the note is "Copyright and hosting; some tutorials stay locked."

**Caption**  
None. Squat setup shows the text 8:12. Hinge pattern shows 6:40. Push-up path shows 5:05. Each of those is a `text-caption` paragraph. There is no subtitle file.

**Transcript**  
None.

**Control**  
Squat setup, Hinge pattern, and Push-up path each have an "Open video" link to `#player`. That player is the Squat setup video above. Paused squat loading, Single-leg hinge, and Press variations have no link and no `video`.

**Motion**  
Nothing plays.

**Fallback**  
No video file for these titles.

**Privacy**  
The links stay on `media.html`.

### YouTube

`planning-brief-starter/acceptance-criteria-template.md` says Home and About should use a YouTube embed instead of a local video file. The pages have no `iframe`. About has a link named "YouTube technique library" with `href="#"`.

**Caption**  
None.

**Transcript**  
None.

**Control**  
None. There is no embed.

**Motion**  
None.

**Fallback**  
Home and About use the poster on the `video` elements above.

**Privacy**  
No YouTube address is in the page, so the page does not contact YouTube.

### Press motion

**Caption**  
None.

**Transcript**  
None.

**Control**  
The shift runs on press of a button or a nav link.

**Motion**  
`states.css` sets `transform: translateY(1px)` on `.button:active` and `.nav-list a:active`. Inside `@media (prefers-reduced-motion: reduce)` that transform is `none`. `testing-evidence.md` recorded the shift off with that preference on, and 1px with it off. There is no `@keyframes` rule.

**Fallback**  
With reduced motion, the control stays in place.

**Privacy**  
None. This is CSS on the page.

## Typography

`body` uses `--font-family`. There is no `@font-face` and no font file in the project. `testing-evidence.md` recorded no web font load and no font swap.

### Body

**Font**  
Arial

**Source**  
On this Mac, Arial Regular is `/System/Library/Fonts/Supplemental/Arial.ttf`. Arial Bold is `Arial Bold.ttf` in that folder. Helvetica is `/System/Library/Fonts/Helvetica.ttc`.

**License**  
Not recorded.

**Fallback stack**  
`Arial, Helvetica, sans-serif`

**Weights and styles**  
The stylesheet sets `font-weight: 700` on `.site-logo`, `.nav-list a`, `.button`, `.badge`, `.field label`, `.field-error`, `.price-table td::before`, and `.price-table .is-tbd`. It does not set `font-style`. It does not set a weight on `body`, `h1`, `h2`, or `h3`. On Home in Chrome, body text computed to 400 normal and the headings computed to 700 normal. The painted family matched Arial, not Helvetica.

**Loading strategy**  
No download. The browser uses the first installed face in the stack.

### Futura

`--font-futura` is not used by an element.

**Font**  
Futura

**Source**  
`/System/Library/Fonts/Supplemental/Futura.ttc`

**License**  
Not recorded.

**Fallback stack**  
`Futura, "Avenir Next", sans-serif`. Avenir Next is `/System/Library/Fonts/Avenir Next.ttc`.

**Weights and styles**  
Not applied. That Futura file has Medium, Medium Italic, Bold, Condensed Medium, and Condensed ExtraBold.

**Loading strategy**  
No `@font-face`. Nothing is downloaded.

## Optimization risks

### Training space pictures

Accessibility. About has four `div` elements with `role="img"`. The labels are a squat rack with a barbell, a laptop, dumbbells and a bench, and a notebook with lift cues. Each box is the flat fill `#d4d0c8`. There is no image file.

Layout. `testing-evidence.md` recorded the boxes at 8rem from the start and a layout shift score of 0. A later photo has no recorded pixel size.

### Video elements

Accessibility. Home, About, and the Media player each expose `controls`. Each one has no `src`, no `track`, and no transcript.

Performance. `planning-brief-starter/acceptance-criteria-template.md` says a local video file would make the company name and navigation wait on that download. There is no video file in the project. The poster is `images/video-placeholder.svg`, 148 bytes, 1600 by 900. `testing-evidence.md` recorded the 16:9 frame before the poster and a layout shift score of 0. Home was 1120 by 630, About was 602 by 339, and Media was 864 by 486.

### YouTube embed

Performance. The same criteria says Home and About should use a YouTube embed. The pages have no `iframe`. `testing-evidence.md` recorded that nothing embedded pushes the page. The request size of that embed is not recorded.

## Evidence plan

Chrome. Home, About, Media, and Services.

### File size

I will read the byte size of `CSS Architecture Package/images/video-placeholder.svg` and `CSS Architecture Package/images/card-two-widths.png`. I will look through that images folder for a training-space photo and a video file.

### Dimensions

I will read the SVG `width` and `height`, and the PNG pixel size. In DevTools I will measure `.media-object__frame` on Home, About, and Media at 375px, 768px, and 1280px, and check that each frame stays 16:9. I will measure `.gallery-item__image` on About and check the height against 8rem.

### Responsive behavior

At 375px, 768px, and 1280px I will check that the poster stays inside the frame and the page does not scroll sideways. I will count the About gallery columns at each width. I will check that the About video sits above the bio until the container is over 64rem, and beside the bio after that.

### Loading

On each page I will open the Network panel and reload. I will list any request for the poster SVG, a video file, a font file, or a YouTube host. I will check the page source for `@font-face`, a font stylesheet, and an `iframe`.

### Accessibility

I will tab to each `video` and read its accessible name. I will look for a `track` and a transcript on Home, About, and the Media player. On About I will read the four `role="img"` names in the accessibility tree. With `prefers-reduced-motion: reduce` on, I will press a button and a nav link and check the 1px shift.
