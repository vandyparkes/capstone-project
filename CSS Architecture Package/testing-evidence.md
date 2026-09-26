# Testing evidence

Chrome. Home, Media, Services, and About.

## Narrow (375px)

No sideways scroll.

The header wraps. Logo on one line. Home, Media, Services, and About on the next.

“Bulletproof Personal Training” wraps to two lines. “Advanced and locked tutorials” wraps to two lines. “Beginner and advanced coaching” wraps to two lines.

“YouTube technique library” and “Request a private session” stay on one line.

“Watch tutorials” and “Request a session” stack.

Cards stay one column. Badges stack inside the card. “Members only” stays on its own row.

Form fields fill the form. The required labels stay on one line. The email error wraps to two lines.

Services pricing stacks. Type, Access, Price, and Notes stay in one block. “Travel radius confirmed by email” stays with that row.

About video sits above the bio.

## Medium (768px)

Still no sideways scroll.

The header fits one row.

Home value cards go two across. The three teasers wrap to two, then one.

The content box is 721px, under 48rem, so the pricing rows stay stacked. “Travel radius confirmed by email” fits on one line in that stack.

The About video is still stacked. The gallery is two across.

## Wide (1280px)

Still no sideways scroll.

The header fits one row.

“Advanced and locked tutorials” fits on one line. Media badges sit on one row. “Members only” sits beside “Advanced.”

Two-up and three-up cards sit in a row. The About gallery is four across.

The pricing table is a table again. “Travel radius confirmed by email” and “Locked tutorials stay labeled until the rate is published” each fit on one line.

The video sits beside the bio.

“YouTube technique library” and “Request a private session” stay on the page.

## 200% zoom / reflow

I set the window to 640px, which is a 1280px window at 200%.

On Home, “Bulletproof Personal Training” fits on one line. “Watch tutorials” and “Request a session” sit on one row. The header fits one row. No sideways scroll.

## Long headings, long links, dense cards, forms, tables, and navigation

Long headings wrap when the line is full. At 375px the three long headings above wrap to two lines. At 640px and 1280px they fit on one line.

Long links stay inside the column. The About links stay on one line at 375px and 1280px. The Home buttons stack at 375px and share a row at 640px.

Dense cards keep the badges, title, time, sentence, and link inside the card. Badges stack at 375px and share a row at 1280px.

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
