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
