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
   The page background is a warm off-white, `#f5f3ef`. Cards and the form are white, `#ffffff`. Body text is near-black, `#1b1b1b`. Extra notes are gray, `#5a5a5a`. The main accent is dark red, `#9b1c1c`, with white text on red buttons. Warning text is brown, `#7a4500`. That brown is for “TBD after consultation” and form errors. Borders are gray, `#8a877e`. The Beginner badge is dark green, `#0d5c46`. The Advanced badge is dark blue, `#163a5f`. Free uses the dark red. Members only uses the gray. Every page uses this same set.

2. **Typography**  
   The font is Futura. Regular text is Futura Medium. Headings, the logo, the nav, and buttons are Futura Bold. If Futura is missing, the page uses Atkinson Hyperlegible, then Arial. The page title is the largest text. Section headings are next. Card titles are a little bigger than body text. Long paragraphs stop before they run across the whole screen. Captions, video times, and badges are slightly smaller than body text.

3. **Spacing**  
   Spacing uses five steps: 8, 16, 24, 32, and 48 pixels. Small space goes inside a card. Medium space goes between cards. The largest step goes between sections. Home and Services use the same section spacing.

4. **Max-widths**  
   The header, main content, and footer sit in one centered column. Paragraphs stay narrow enough to read. The Media player is a little narrower than that column. The request form is narrower than the player. On a wide About page, the video sits beside the bio. On a narrow page, they stack.

5. **Borders**  
   Cards, the pricing table, and form fields share one gray border and the same rounded corners. Buttons use a dark red border. The training note adds a brown bar on the left. Locked tutorial cards keep the same border as the other cards.

6. **Focus**  
   Keyboard focus shows a dark red outline on nav links, buttons, and form fields. The outline is easy to see. Tab order follows the page: header, main content, form, then footer.

7. **Links**  
   Text links are dark red. Nav links are near-black. On hover, nav links, buttons, card links, and the About platform link get an underline. The current page in the nav is dark red and underlined. The main button is dark red with white text. The second button is white with dark red text. Footer links stay text links.

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

## 6. Risk note

Media tutorial cards and the Services session cards, pricing table, and request form.

One card pattern covers the three-column grids, the Beginner, Free, Advanced, and Members only badges, and the free and locked copy. Services adds the four-column pricing table and the request form under those cards. At about 375px and about 768px the cards and the table stack. On a wide screen the cards sit in a row and the table sits under them.
