# Layout Risk and Breakpoint Inventory

Bulletproof PT

This is from the planning package and the CSS that is already in the architecture folder. Nothing in the site files was changed.

I am only writing the first part for now.

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
