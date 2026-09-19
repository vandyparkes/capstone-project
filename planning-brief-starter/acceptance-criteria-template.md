# Acceptance Criteria Starter

Use this structure:

> When [condition], [content/component/page] must [observable behavior] so that [user/task/quality goal]. I will test this by [test method].

## Criteria Drafts

Responsive:  
When the browser is about 375px wide, the Home nav must stay on screen with no sideways scroll and still show Media, Services, and About so a phone visitor can move between pages. I will test this by shrinking the window or using DevTools at 375px and checking that nothing is cut off.

Responsive:  
When the viewport is about 768px wide, the Services session types and video vs in-person prices must stack into a readable column instead of overlapping so a visitor can compare coaching options. I will test this by setting DevTools to a tablet width and reading the session list and prices with no zoom and no side scroll.

Accessibility:  
When a visitor uses only the keyboard, every control in the session-request form (name, email, area of interest) must get a visible focus outline in a logical order, and each field must be tied to a `<label>` with matching `for` and `id` so they can request a session without a mouse. I will test this by tabbing through the form and checking each input’s label in the inspector.

Accessibility:  
When a visitor opens About or Home, the page must use one `<h1>` for the page title (trainer or company name), then `<h2>` / `<h3>` in order, with main content in `<main>` and site links in `<nav>`, so a screen reader can reach the trainer bio and tutorials. I will test this by checking the heading outline and landmarks in the Accessibility pane or a headings bookmarklet.

Browser support or fallback:  
When the highlight or intro video cannot play, the Home (and About) video area must still show a poster image with alt text plus a short text summary of the trainer intro so visitors can still learn who the trainer is. I will test this by opening the page in a second browser and by temporarily renaming the video file to confirm the image and text stay.

Performance:  
When Home (and About) load the highlight or intro video, the page must use a YouTube embed instead of a local video file so the company name and navigation show without waiting on that download. I will test this by checking the page source for a YouTube embed to confirm the site is not serving the video file itself.

Metadata or discoverability:  
When a visitor looks at a browser tab or page source, each of Home, Media, Services, and About must have a unique `<title>` that includes “Bulletproof Personal Training” and what that page is for, plus a short `<meta name="description">` so the pages can be told apart in search and bookmarks. I will test this by reading the tab title on every page and viewing source for the title and description tags.

Release quality:  
When the site is ready to share, every nav link must open the correct page (no missing files), beginner vs advanced tutorial labels on Media must match the headings on the page, and the request form must include only name, email, and area of interest (no health or payment fields) so a visitor can browse tutorials and ask for a session. I will test this by clicking every navigation link, comparing labels to headings, and checking the form fields in the browser.