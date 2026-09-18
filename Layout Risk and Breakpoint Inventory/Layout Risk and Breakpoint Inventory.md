# Layout Risk and Breakpoint Inventory

Bulletproof PT

## 1) Layout patterns

1. **Header and navigation**  
   Same header on every page. The logo sits on one side. Home, Media, Services, and About sit on the other. That is `.site-header` and `.nav-list`. Both wrap. The browser places the next link in the next space. No link is pinned to a named grid cell.

2. **Home hero**  
   The company name, a short pitch, two buttons, and the highlight video. This is the first thing someone sees on Home. The content container already uses a flexible constraint: `width: min(100% - 2rem, 70rem)`.

3. **Card grids**  
   Same card, different counts. Two across for the home value props and the quotes. Three across for teasers, tutorials, and session types. Four across for the About gallery. Tracks are flexible (`1fr`). Cards stay in document order. A mixed track such as `minmax()` would fit better when a card’s own min-content width is wider than an equal share of the row. Gallery captions and stacked card rows (badge, title, duration, sentence, link) are the place subgrid would help if those inner lines need to line up across a row.

4. **Media and text split**  
   On About, the intro video sits beside the bio and credentials. That is `.media-split`, a mixed track (`1.2fr 1fr`) once there is enough inline space. On Media, the player sits with the technique notes. That is `.media-object` inside the narrower `.container--media`, which uses `min(100% - 2rem, 54rem)`.

5. **Pricing table**  
   Type, Access, Price, and Notes. One table, class `.price-table`.

6. **Session request form**  
   Name, email, and area of interest. That is `.session-form`.

7. **Resource list**  
   The platform links on About. That is `.resource-list`.

8. **Training note**  
   The warning on Media. It is an aside with the `.callout` class.

## 2) Content risks

These are the pieces most likely to break a layout if the CSS ignores the content’s natural size.

1. **Long headings**  
   “Bulletproof Personal Training,” “Advanced and locked tutorials,” and “Beginner and advanced coaching.” At about 375px they wrap and eat vertical space. The heading’s min-content width is the risk.

2. **Long links**  
   “YouTube technique library,” “Instagram session notes,” “Request a private session,” and “Back to tutorials.” They can overflow a narrow column if wrap or shrink is wrong.

3. **Dense cards**  
   Media tiles stack two badges, a title, a duration, a sentence, and a link. Locked cards use “Members only,” which is longer than “Free.” Three of those in a row get tight before the screen is actually small. Badges already use `width: fit-content`. The card’s min-content width should decide when the row wraps.

4. **Pricing table**  
   Four columns. The Notes cells are already long: “Travel radius confirmed by email” and “Locked tutorials stay labeled until the rate is published.” In a row, prices can pull away from their session type, and the table can clip. That is the 375px and print risk.

5. **Form**  
   Labels include “(required).” The email error is a full sentence. Fields need to stay full width so the label, control, and error do not collide.

6. **Embedded video**  
   16:9 video on Home, About, and the Media player. Without a contained frame, it goes full-bleed or overflows.

7. **Header cluster**  
   “Bulletproof PT” plus four nav words. Sideways scroll is the 375px failure the plan forbids.

8. **Two CTAs**  
   “Watch tutorials” next to “Request a session.” They wrap or overflow if they are treated as one unbreakable row.

9. **Gallery**  
   Four captioned tiles. The captions wrap under short image boxes, so caption height will not match from tile to tile.

## 3) Breakpoint reasons

The layout should change when content becomes cramped, awkward, unreadable, or inefficient, not because a phone or laptop width was chosen in advance. Use a viewport media query when the window or print matters. Use a container query when one component should follow its own box. Spacing and containers can stay fluid with `min()` instead of jumping only at those widths.

1. **Header and nav, about 375px**  
   The logo and four page names have to stay on screen with no sideways scroll. The row wraps. It does not stay one forced horizontal bar. That is already how `.site-header` and `.nav-list` work. The viewport matters here, so a media query is enough.

2. **Pricing table, before about 48rem**  
   Four columns plus long Notes text. In a row, the price can pull away from its session type, and the table can clip, including in print. Below 48rem, the visual header hides and each cell stacks with `data-label` so Type, Access, Price, and Notes stay one unit. Example: `@media (width >= 48rem)`.

3. **3-up and 4-up cards, before about 64rem**  
   Tutorial and session cards carry badges, titles, and a sentence. Four gallery tiles plus captions cannot stay readable as equal columns. They go one column until there is enough room. Two-up is different. Short Home value props and quotes can sit two across at 48rem.

4. **About video and bio, before about 64rem**  
   A 16:9 frame plus a bio and credentials list. Side by side too early squeezes the video or the text. The video stacks above the bio until both have enough inline space. That is the `.media-split` rule at 64rem.

## 4) Container-query candidates

A container query answers how wide the component is, not how wide the window is.

1. **`.card`**  
   Same card in 2-up, 3-up, and 4-up tracks, plus locked versus free. A viewport query cannot tell a card it is sitting in a narrow third of the page versus a full-width stack. Give the card `container-type: inline-size`. Padding, badge wrap, and whether the body stays one column should follow the card, for example `@container (width > 34rem)`.

2. **`.media-object`**  
   Full width in the Home hero, half of a split on About, and inside the narrower `.container--media` player. Gap and whether notes sit beside or under the frame should follow that box, not only the window. Same setup: `container-type: inline-size`, then a container query when the object is wide enough for two columns.

The site header is not a container-query candidate. It is not reused at several widths on one page. A viewport query is enough.

## 5) Logical-property opportunities

Prefer inline and block when spacing, sizing, and borders should follow writing mode. Some flow-relative CSS is already in place: `margin-inline`, `margin-block`, `padding-block`, and `margin-inline-start`. These leftovers still assume left-to-right English.

1. **`.callout { border-left }`**  
   Change to `border-inline-start` so the warning bar stays on the start edge.

2. **`.price-table { text-align: left }`**  
   Change to `text-align: start`.

3. **Heading, paragraph, card, and list spacing**  
   `margin-top` and `margin-bottom` become `margin-block-start` and `margin-block-end`. Same for `.site-footer`, `.resource-list li`, gallery captions, and stacked table cells.

4. **`.site-footer { border-top }`**  
   Change to `border-block-start`.

5. **`.skip-link { top; left }`**  
   Change to `inset-block-start` and `inset-inline-start`.

6. **Width on measure, form, and containers**  
   `max-width` and `width` can become `max-inline-size` and `inline-size` so the reading measure follows the writing mode.

## 6) Preference and fallback needs

1. **`prefers-reduced-motion`**  
   Buttons and nav use `transform: translateY(1px)` on `:active` and `filter` on hover. Those should ease off when the user asks for less motion: `@media (prefers-reduced-motion: reduce)`.

2. **Unplayable or unsupported video**  
   Hosting is still undecided. The layout has to stay readable when `<video>` has no file. Home, About, and the Media player need a poster, an accessible name, and a short text summary.

3. **Form errors cannot be color-only**  
   The warning border stays, and the error text stays visible.

4. **Services print**  
   Hide nav, CTAs, the form, and embeds. Keep headings, session facts, and the table readable. Stack the table so it does not clip. Print is an environment media query, not a container query.

5. **Feature support**  
   `.media-object__frame` uses `aspect-ratio: 16 / 9`. Keep a min-height fallback if an older browser skips the ratio. If cards later use `container-type` or `subgrid`, wrap those rules in `@supports` so the stacked card stays the fallback. Safari and Firefox still need a pass.
