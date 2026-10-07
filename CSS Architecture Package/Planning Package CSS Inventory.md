# Planning Package CSS Inventory

Bulletproof Personal Training

## 1. Repeated components

1. **Navigation**  
   Same header on Home, Media, Services, and About. Logo link reads “Bulletproof PT.” Links stay in this order: Home, Media, Services, About. The current page uses `aria-current="page"`.

2. **Buttons**  
   Home uses a primary link, “Watch tutorials,” and a secondary link, “Request a session.” Services uses the same primary button for “Request a session.” The request form uses a submit button, “Submit request.”

3. **Cards**  
   One card pattern. Home uses it for “What you can do here” and “Start with these pages.” Media uses it for beginner and advanced tutorials. Services uses it for session types. About uses it for beginner and advanced coaching.

4. **Badges**  
   Beginner, Free, Advanced, and Members only. Media tutorial cards use them. About coaching cards use Beginner and Advanced.

5. **Table**  
   Services pricing table. Columns: Type, Access, Price, Notes.

6. **Form**  
   Session request on Services. Fields: name, email, area of interest. Each field has a visible label. Required is written in the label.

7. **Media blocks**  
   A 16:9 frame with a caption or a short note. Home highlight video, About intro video, Media tutorial images, and the Media player.

8. **Resource list**  
   About, “Other platforms.” Two items: “YouTube technique library” and a link, “Request a private session.”

9. **Callout**  
   Media, “Training note.” One heading and one paragraph.

10. **Gallery**  
    About, “Training spaces.” Four figures. Each figure has an image and a caption.

11. **Footer**  
    One line on every page, with one text link.

## 2. Foundational decisions

1. **Color**  
   One background. One card surface. One body text color. One muted text color. One accent for primary buttons and the current nav link. One warning color for “TBD after consultation” and the Media training note. Beginner and Advanced use two separate colors. Every page uses this set.

2. **Typography**  
   One size each for h1, h2, and h3. One body style. The site name and section titles stay readable at about 375px. Bios, technique notes, and session copy use one line-height and a max line length. Duration, prices, and badges use a smaller caption size.

3. **Spacing**  
   One scale: 8, 16, 24, 32, 48. Card padding, grid gaps, and section space come from that scale. Home and Services use the same vertical rhythm.

4. **Max-widths**  
   One content width for the header, main, and footer. The name, video, and pricing table stay inside it. The Media player and the About video-and-bio pair use a narrower width than body copy.

5. **Borders**  
   One radius. One solid border for cards, the pricing table, and form fields. Locked tutorial cards use that same border. The badge and the copy mark them as locked.

6. **Focus**  
   One visible outline on nav links, buttons, text fields, the select, and the submit button. Focus order follows the page: header, main, form, footer.

7. **Links**  
   Text links have a default style and a hover style. Nav adds a current-page style. Buttons stay separate from text links. About platform links and footer links stay text links.

## 3. Layout and composition

1. **Page shell**  
   Header, main, and footer repeat on Home, Media, Services, and About. Each page has one h1. The Media player stays on Media: back link, frame, and notes. It is not its own page.

2. **Containers**  
   One centered content width on the header, main, and footer. The Media player uses the narrower width.

3. **Section spacing**  
   The same vertical space between the intro, card groups, table, media, training note, gallery, and form.

4. **Grids**  
   Two columns: Home “What you can do here,” and About beginner and advanced coaching.  
   Three columns: Home “Start with these pages,” Media beginner tutorials, Media advanced tutorials, and Services session types.  
   Four columns: About “Training spaces.”  
   About video and bio sit side by side when the row is wide enough, and stack when it is not.  
   Card grids go to one column on a narrow screen.

5. **Clusters**  
   Home: name, short pitch, two buttons, highlight video, two-column cards, three-column cards.  
   Media: beginner tutorials, advanced and locked tutorials, training note, player.  
   Services: session-type cards, pricing table, request form.  
   About: intro video and bio, coaching cards, platform list, gallery.

6. **Narrow, about 375px**  
   The nav wraps and stays on the screen. Sections are one column. Form fields are full width. Each pricing row keeps Type, Access, Price, and Notes together.

7. **Medium, about 768px**  
   Session cards and the pricing table stay stacked and do not overlap. Video and the text next to it stay stacked.

8. **Wide**  
   Nav sits in one row. The About video can sit beside the bio. Session cards and tutorial cards can sit in a row. The pricing table sits full width under the session cards. The request form stays under the table.

## 4. States

1. **Hover**  
   Nav links, primary and secondary buttons, links inside cards, and the About platform link.

2. **Focus**  
   The outline from part 2, on nav links, buttons, text fields, the select, and submit.

3. **Active**  
   A pressed look on buttons and nav links.

4. **Current page**  
   The nav link with `aria-current="page"` uses the accent color and an underline.

5. **Required and invalid**  
   Name, email, and area of interest are required. Each label includes “(required).” Email uses `type="email"`. An invalid field shows its error sentence with the warning border. The email error on the page reads “Enter a valid email we can reply to.”

6. **Disabled**  
   No field or button is disabled. Locked tutorials stay cards with the Advanced badge, the Members only badge, and the locked copy.

7. **Empty**  
   Each Services price reads “TBD after consultation.” The Media player shows the placeholder image and the squat setup note.

## 5. Print needs

1. **Services**  
   Services is the page that prints. Headings, session types, and the pricing table stay. Each row stacks so Type, Access, Price, and Notes stay together. Text is black on white.

2. **Hidden in print**  
   The nav, buttons, the request form, and video frames.

3. **Other pages**  
   Home, About, and the Media player are watched in the browser. They do not get a separate print layout.
