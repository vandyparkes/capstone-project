# Testing evidence

Chrome. Home, Media, Services, and About.

## Narrow (375px)

No sideways scroll.

The header wraps. Logo on one line. Home, Media, Services, and About on the next.

“Bulletproof Personal Training” wraps to two lines. “Advanced and locked tutorials” wraps to two lines. “Beginner and advanced coaching” wraps to two lines.

“YouTube technique library” and “Request a private session” stay on one line.

“Watch tutorials” and “Request a session” stack.

Cards stay one column. Badges share a row. “Members only” sits beside “Advanced.”

Home, About, and Media frames stay 16:9. Each frame was 343 by 193. The gallery is one across. Each photo was 343 by 229.

Form fields fill the form. The required labels stay on one line. The email error wraps to two lines.

Services pricing stacks. Type, Access, Price, and Notes stay in one block. “Travel radius confirmed by email” stays with that row.

About video sits above the bio.

## Medium (768px)

Still no sideways scroll.

The header fits one row.

Home value cards go two across. The three teasers wrap to two, then one.

The content box is 721px, under 48rem, so the pricing rows stay stacked. “Travel radius confirmed by email” fits on one line in that stack.

The About video is still stacked. The frame was 721 by 406. The gallery is three across, and the fourth photo wraps. Each photo was 230 by 153.

## Wide (1280px)

Still no sideways scroll.

The header fits one row.

“Advanced and locked tutorials” fits on one line. Media badges sit on one row. “Members only” sits beside “Advanced.”

Two-up and three-up cards sit in a row. The About gallery is four across. Each photo was 268 by 179.

The pricing table is a table again. “Travel radius confirmed by email” and “Locked tutorials stay labeled until the rate is published” each fit on one line.

The video sits beside the bio.

“YouTube technique library” and “Request a private session” stay on the page.

## 200% zoom / reflow

I set the window to 640px, which is a 1280px window at 200%.

On Home, “Bulletproof Personal Training” fits on one line. “Watch tutorials” and “Request a session” sit on one row. The header fits one row. No sideways scroll.

The Home frame was 593 by 334. The About frame was 593 by 334 and still stacked. Both stay 16:9. The gallery is two across. Each photo was 289 by 192.

## Long headings, long links, dense cards, forms, tables, and navigation

Long headings wrap when the line is full. At 375px the three long headings above wrap to two lines. At 640px and 1280px they fit on one line.

Long links stay inside the column. The About links stay on one line at 375px and 1280px. The Home buttons stack at 375px and share a row at 640px.

Dense cards keep the badges, title, time, sentence, and link inside the card. Badges share a row at 375px and at 1280px.

The form stays full width at 375px. Required labels stay on one line. The error sentence wraps to two lines.

The table stacks at 375px and 768px. At 1280px it is a table, and the long notes fit on one line.

Navigation wraps at 375px. It fits on one row at 640px, 768px, and 1280px.

## Keyboard focus

Tab order is skip link, logo, nav, then main.

Skip link, nav, buttons, and form fields use the 3px accent outline with a 3px offset.

Services email stays invalid on purpose. Warning border plus the error sentence.

## Preference and fallback

`prefers-reduced-motion: reduce` is on. The 1px press shift on buttons and nav is off. With that preference off, the press shift is 1px.

If `subgrid` is missing, gallery tiles stay in the auto-fill grid. Captions stay under each image.

If the container query is missing, card badges stay stacked. The card is still readable.

## Layout shift

Home, About, and Media. The layout shift score stayed at 0.

Media dimensions. The video frame holds 16:9 before the poster shows. Home was 1120 by 630. About was 602 by 339. Media was 864 by 486. The poster SVG is 1600 by 900, the same ratio, so the poster does not push the text under it. There is no video file, so no later video size arrives. Each gallery `img` has `width="800"` and `height="533"`, and the CSS frame is 3:2 before the JPEG paints.

Font loading. Body type is Atkinson Hyperlegible, then Arial, Helvetica, sans-serif. The 400 file is 11,208 bytes. The 700 file is 11,364 bytes. `font-display` is `swap`. On these reloads the layout shift score stayed at 0.

Embedded content. There is no `iframe` and no `audio`. Nothing embedded pushes the page.

## Slow network

I reloaded Home, About, Media, and Services.

Home, Media, and Services request the stylesheets and both Atkinson woff2 files. Home and Media also request `images/video-placeholder.svg`. About also requests the four gallery JPEGs.

No video file. No YouTube host. The layout shift score stayed at 0.

## Image dimensions and file size

`images/video-placeholder.svg` is 167 bytes, 1600 by 900. It is the poster on Home, About, and Media.

`images/card-two-widths.png` is 35,175 bytes, 812 by 393. It is not placed on Home, About, Media, or Services.

Training spaces photos are JPEG, 3:2. At 1x, a slot under 480px wide requests the 480 file. At 2x on a wide window, the same slot requests the 800 file.

`images/home-gym-800.jpg` is 45,877 bytes, 800 by 533. `images/home-gym-480.jpg` is 23,231 bytes, 480 by 320.

`images/online-800.jpg` is 64,850 bytes, 800 by 533. `images/online-480.jpg` is 30,153 bytes, 480 by 320.

`images/small-space-800.jpg` is 66,853 bytes, 800 by 533. `images/small-space-480.jpg` is 22,995 bytes, 480 by 320.

`images/notes-800.jpg` is 36,568 bytes, 800 by 533. `images/notes-480.jpg` is 15,392 bytes, 480 by 320.

Services has no `img` and no `video`.

## Alt text

The poster is not an `img`, so it has no `alt`.

Home name: “Highlight video placeholder.” About name: “Trainer intro video placeholder.” Media name: “Squat setup video placeholder.”

Gallery alts: "Man holding a loaded barbell across his shoulders in a squat." "Open laptop on a wooden table beside a notebook, a pen, and a phone." "Two adjustable dumbbells and loose plates on a gray floor." "Small blue spiral notepad next to a one-euro coin."

The figcaptions read Home gym coaching, Online sessions, Small-space setup, and Session notes.

## Captions and transcripts

No `track` on Home, About, or the Media player. No transcript.

The Media cards show 8:12, 6:40, and 5:05. Those are the duration lines.

Under the player: “Keep the whole foot on the floor, brace before you sit, and push through the heel on the way up.”
