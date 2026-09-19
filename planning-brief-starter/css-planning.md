# CSS System Planning

## Repeated Components

Header - “Bulletproof PT” Same header on every page- Readable at about 375px.

Primary Navigation - Home, Media, Services, About, in that order. Current-page styling belongs here, not as a one-off per page.

Tables: Services pricing table (Type, Access, Price, Notes) One pattern that stacks on small screens.

Forms: Session Request with visible labels, Production fields stay name, email, area of interest

Badges / Labels - Beginner, Advanced, Free, Locked

## Foundational Decisions

Color: One background. One card surface. One body text. One muted text. One accent for primary CTAs and current nav. One warning color for TBD and risk notes. Beginner and Advanced get two distinct colors that still pass contrast. No new palette per page. No dashed-gray wireframe look in production.

Typography: One heading scale for h1–h3. One body style. Name and titles stay readable at about 375px. Set line-height and a max line length for bios, technique notes, and session copy. Duration, prices, and badges can use a smaller caption size.

Spacing: Use a small scale, like 8 / 16 / 24 / 32 / 48, for card padding, grid gaps, and section space. Home and Services should share the same vertical rhythm.

Max-widths: One content container so the name, video, and tables do not go full-bleed. Video and the pricing table can be a little narrower than body copy. Media and About’s “video + bio” pair share that width.

Borders: One radius. One border or shadow for cards, tables, and inputs. Locked tutorials use the same card with different copy and a badge. Solid borders in production. Dashed Figma lines stay in Figma.

Focus: Visible outline on nav, buttons, fields, selects, and submit. Do not remove it unless you replace it with something equally clear. Focus order follows the page: header, main, form, footer.

Links: Default, hover, and current-page nav. Buttons stay distinct from text links. About and footer links look like links, not a third button style.

## Layout / Composition needs

Shared page shell

Header (logo and nav) – `<main>` with one `<h1>` – footer

Repeat on all four pages

The media player view stays inside media (back link + embed + notes), not a fifth site page

Containers

One centered content width

Inner clusters for “video + short copy,” “session cards + pricing table,” and “form”

Section Spacing

Consistent vertical rhythm between hero, card grids, tables, media, and the form

Four pages should feel like one site

Grids (from the figma, stacked on small screens)

2-up: home value props; about video + bio: home testimonials

3-up: home teasers: media tutorial cards; services session types

4-up: about platform cards and gallery

### Responsive Stacks

Narrow (~375px)

Nav stays on screen with no sideways scroll

Media, services, and about remain visible

Everything else is one column

Form fields full width

Tables stack so each price stays attached to its recession

Medium (~768px)

Session types and prices still stack or become a simple stacked card list

They must not overlap

Video and supporting text stay stacked

Wide

Nav horizontal. Video may sit beside bio/copy.

Session cards and tutorial cards can sit in a row.

Pricing table may sit full width under the cards

Booking is a cluster: request form

### Clusters

Home: name and highlight video + two CTAs to value props to teasers to optional testimonials

Media: beginner group then advanced/locked group then optional risk note then player view hen a free video is opened

Services: session-type cards then pricing table, request form

About: intro video + bio to credentials then beginner/advanced coaching to platform links and then gallery.

## States

There is no login, paid or live-calendar state

Hover: nav links, primary and secondary buttons. Free tutorial cards, Home teasers, About platform links

Focus: Keyboard outline or nav, buttons, form fields, and submit

Active: Pressed look for buttons and nav

Required / Invalid form: Name, email, area of interest with visible labels; Mark required fields, required and type=”email”. Error text cannot be color-only.

Disabled: only if a control is truly usable. Do not style locked tutorials as disabled buttons that look unlockable. Locked versus free is copy + badge for premium members

Empty / fallback: Unplayable video gets a poster, alt, and text summary on Home, About, and the media player. Missing images do not ship without alt and licensing. Empty Media list gets a short “tutorials coming soon” note if content is still missing. “Rate TBD” is an empty price state on Services. Not a new component.

Locked vs. Free: Figma shows play vs. lock, beginner vs advanced, “Members Only.” In production, keep distinction in labeling and copy.

Static form: Requests only, no payment, no waiver until legal review.

## Print needs

Services should print cleanly. Someone may print or save-to-PDF the options before requesting a session.

For print: hide nav, CTAs, and video embeds; keep headings, session facts and the table readable in high contrast; do not let the wide table clip. Stack rows if needed

Home/About video, the Media player, and tutorial cards do not need rich print. If you skip print CSS elsewhere, that is reasonable: the site is for watching and requesting in the browser. Do not print the waiver until C11 is reviewed

## Risk Note

Media tutorial cards plus Services session cards/tables are the area most likely to get messy

Figma gives those two areas the most variants: 3-up cards, badges, free vs locked, beginner vs advanced, a separate pricing table, and a form next to booking placeholders

If you style each tile one-off, you will fight the 375px/768px stacking rules
