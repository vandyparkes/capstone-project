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
