# Layout Risk and Breakpoint Inventory

Bulletproof PT

This is from the planning package and the CSS that is already in the architecture folder. Nothing in the site files was changed.

## 1) Layout patterns

These are the layouts that keep showing up. They already have a home in the HTML and CSS.

1. **Header and nav**  
   Same header on every page. Logo on one side, Home, Media, Services, and About on the other. That is `.site-header` and `.nav-list`.

2. **Home hero**  
   The company name, a short pitch, two buttons, and the highlight video. This is the first thing someone sees on Home.

3. **Card grids**  
   Same card, different counts. Two across for the home value props and the quotes. Three across for teasers, tutorials, and session types. Four across for the About gallery.

4. **Video next to text**  
   On About, the intro video sits beside the bio and credentials. That is `.media-split`. On Media, the player sits with the technique notes. That is `.media-object` inside the narrower `.container--media`.

5. **Pricing table**  
   Type, Access, Price, and Notes. One table, class `.price-table`.

6. **Session request form**  
   Name, email, and area of interest. That is `.session-form`.

7. **Resource list**  
   The platform links on About. That is `.resource-list`.

8. **Training note**  
   The warning on Media. It is an aside with the `.callout` class.

## 2) Content risks

These are the pieces most likely to break a layout if the CSS assumes short, tidy copy.

1. **Long headings**  
   “Bulletproof Personal Training,” “Advanced and locked tutorials,” and “Beginner and advanced coaching.” At about 375px they wrap and eat vertical space.

2. **Long links**  
   “YouTube technique library,” “Instagram session notes,” “Request a private session,” and “Back to tutorials.” They can overflow a narrow column if wrap or shrink is wrong.

3. **Dense cards**  
   Media tiles stack two badges, a title, a duration, a sentence, and a link. Locked cards use “Members only,” which is longer than “Free.” Three of those in a row get tight before the screen is actually small.

4. **Pricing table**  
   Four columns. The Notes cells are already long: “Travel radius confirmed by email” and “Locked tutorials stay labeled until the rate is published.” In a row, prices can pull away from their session type, and the table can clip. That is the 375px and print risk the plan already names.

5. **Form**  
   Labels include “(required).” The email error is a full sentence. Fields need to stay full width so the label, control, and error do not collide.

6. **Embedded video**  
   16:9 video on Home, About, and the Media player. Without a contained frame, it goes full-bleed or overflows.

7. **Header cluster**  
   “Bulletproof PT” plus four nav words. Sideways scroll is the 375px failure the plan forbids.

8. **Two CTAs**  
   “Watch tutorials” next to “Request a session.” They wrap or overflow if they are treated as one unbreakable row.

9. **Gallery**  
   Four captioned tiles. The captions wrap under short image boxes.

## 3) Breakpoint reasons

The layout should change when the content stops fitting, not because a device name suggested a number.

1. **Header and nav, about 375px**  
   The logo and four page names have to stay on screen with no sideways scroll. The row wraps. It does not stay one forced horizontal bar. That is already how `.site-header` and `.nav-list` work.

2. **Pricing table, before about 48rem (768px)**  
   Four columns plus long Notes text. In a row, the price can pull away from its session type, and the table can clip, including in print. Below 48rem, the visual header hides and each cell stacks with `data-label` so Type, Access, Price, and Notes stay one unit.

3. **3-up and 4-up cards, before about 64rem**  
   Tutorial and session cards carry badges, titles, and a sentence. Four gallery tiles plus captions cannot stay readable as equal columns. They go one column until there is enough room. Two-up is different. Short Home value props and quotes can sit two across at 48rem.

4. **About video and bio, before about 64rem**  
   A 16:9 frame plus a bio and credentials list. Side by side too early squeezes the video or the text. The video stacks above the bio until both have enough inline space. That is the `.media-split` rule at 64rem.

## 4) Container-query candidates

1. **`.card`**  
   Same card in 2-up, 3-up, and 4-up tracks, plus locked versus free. A viewport query cannot tell a card it is sitting in a narrow third of the page versus a full-width stack. Padding, badge wrap, and whether the link stays on one line should follow the card width.

2. **`.media-object`**  
   Full width in the Home hero, half of a split on About, and inside the narrower `.container--media` player. Gap and whether notes sit beside or under the frame should follow that box, not only the window.

The site header is not a container-query candidate. It is not reused at several widths on one page. A viewport query is enough.

## 5) Logical-property opportunities

Some flow-relative CSS is already in place: `margin-inline`, `margin-block`, `padding-block`, and `margin-inline-start`. These leftovers still assume left-to-right English.

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
