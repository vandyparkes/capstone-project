# Layout Risk and Breakpoint Inventory

Bulletproof PT

## 1) Layout patterns

1. **Navigation**  
   Same header on every page. Logo on one side. Home, Media, Services, and About on the other.

2. **Hero**  
   Company name, short pitch, two buttons, and the highlight video on Home.

3. **Card grid**  
   Same card, different counts. Two across for value props and quotes. Three across for teasers, tutorials, and session types. Four across for the About gallery.

4. **Media / text split**  
   About video beside the bio. Media player beside the technique notes.

5. **Table**  
   Services pricing table: Type, Access, Price, and Notes.

## 2) Content risks

1. **Long headings**  
   “Bulletproof Personal Training” and “Advanced and locked tutorials” wrap at about 375px because that is their natural width.

2. **Long links**  
   “YouTube technique library” and “Request a private session” can overflow a narrow column.

3. **Dense cards**  
   Tutorial cards stack two badges, a title, a duration, a sentence, and a link. “Members only” is longer than “Free,” so the card’s natural width gets tight before the window is small.

4. **Table**  
   Four columns. Notes such as “Travel radius confirmed by email” make the row clip or pull the price away from the session type.

5. **Form**  
   Labels include “(required).” The email error is a full sentence. Fields need to stay full width.

6. **Embedded media**  
   16:9 video on Home, About, and the Media player can go full-bleed or overflow without a contained frame.

## 3) Breakpoint reasons

Layout should change when content is cramped, awkward, or unreadable, not because a phone or laptop width was chosen first.

1. **Header and nav**  
   The logo plus four page names do not fit one row at about 375px. The row needs to wrap so the page does not scroll sideways.

2. **Pricing table**  
   Four columns plus long Notes text get cramped before about 48rem. Each row should stack so Type, Access, Price, and Notes stay one unit.

3. **Card grids and the About video/bio**  
   Three tutorial cards and four gallery tiles get unreadable as equal columns before about 64rem. A 16:9 video beside a bio squeezes both too early. They should stack until there is enough inline space.

## 4) Container-query candidates

**`.card`**  
The same card sits in 2-up, 3-up, and 4-up tracks. A viewport query cannot tell a card it is in a narrow third of the page versus a full-width stack. Give it `container-type: inline-size` so padding and badge wrap follow the card, for example `@container (width > 34rem)`.

## 5) Logical-property opportunities

1. **`.callout { border-left }`**  
   Change to `border-inline-start`.

2. **`.price-table { text-align: left }`**  
   Change to `text-align: start`.

3. **`margin-top` / `margin-bottom` on headings, paragraphs, and lists**  
   Change to `margin-block-start` and `margin-block-end`.

## 6) Preference and fallback needs

**`prefers-reduced-motion`**  
Buttons and nav use `transform: translateY(1px)` on press. That motion should ease off when the user asks for less motion.
