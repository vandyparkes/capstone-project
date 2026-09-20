# Testing evidence

Chrome. Home, Media, Services, and About.

## Narrow (375px)

No sideways scroll.

The header wraps. Logo on one line. Home, Media, Services, and About on the next.

Cards stay one column. “Bulletproof Personal Training” wraps in place.

Services pricing stacks. Type, Access, Price, and Notes stay in one block.

About video sits above the bio.

Media badges stack inside the card. “Members only” stays on its own row.

## Medium (768px)

Still no sideways scroll.

The header fits one row.

Home value cards go two across. The three teasers wrap to two, then one.

The pricing table is a table again. Notes stay in the last column.

The About video is still stacked. 768 is under 64rem.

## Wide (1280px)

Still no sideways scroll.

Two-up and three-up cards sit in a row. The About gallery is four across.

The video sits beside the bio.

Media badges sit on one row when the card is wide enough.

## 200% zoom / reflow

I zoomed a 1280px window to 200% (about 640px).

Copy reflowed. Grids dropped columns. No sideways scroll.

## Keyboard focus

Tab order is skip link, logo, nav, then main.

Skip link, nav, buttons, and form fields use the 3px accent outline with a 3px offset.

Services email stays invalid on purpose. Warning border plus the error sentence.

## Preference and fallback

`prefers-reduced-motion: reduce` is on. The 1px press shift on buttons and nav is off.

If `subgrid` is missing, gallery tiles stay in the auto-fill grid. Captions stay under each image.

If the container query is missing, card badges stay stacked. The card is still readable.
