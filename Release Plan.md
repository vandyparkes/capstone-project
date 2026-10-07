# Release plan

Site files: `site/`.

## 1. Final page list

These four files are the submitted pages. Each one is linked from the main nav.

1. Home. `index.html`. Title: `Home | Bulletproof Personal Training`. Heading: `Bulletproof Personal Training`.
2. Media. `media.html`. Title: `Media | Bulletproof Personal Training`. Heading: `Media`.
3. Services. `services.html`. Title: `Services | Bulletproof Personal Training`. Heading: `Services`.
4. About. `about.html`. Title: `About | Bulletproof Personal Training`. Heading: `About the trainer`.

Nav order on each page: Home, Media, Services, About. The logo links to `index.html`.

The squat player is a section on `media.html` (`#player`). It is the same file. There is no fifth HTML page.

## 2. Must-fix list

Priority is High or Medium. Owner is this project.

1. **High.** Beginner tutorials on Media do not play. `site/media.html` `#player` is a `video` with `poster="images/video-placeholder.svg"`. It has no `src` and no `source`. Squat setup links to `#player` with `Open video`. Hinge and Push-up path have no link and no `video`. Action: put a source on the Squat setup player, or take `Open video` off until that source is in the file. Hinge and Push-up path stay text until each one has its own clip.

2. **High.** The session form opens on an error. `site/services.html` sets the email field to `not-an-email`, `aria-invalid="true"`, and `is-invalid` on its parent. `.field.is-invalid .field-error` is `display: block`, so `Enter a valid email we can reply to.` is on screen before a visitor types. Action: start that field empty, with `aria-invalid="false"` and without `is-invalid`.

3. **High.** A valid submit leaves the page. The form is `method="post"` and `action="#"`. The script does not listen for `submit`. `Discoverability and Structured Content.md` records the file server response `501` and `Unsupported method ('POST')`. The page has no confirmation text. Action: keep a valid submit on `services.html` and show a result on that page.

4. **Medium.** The clips have no caption track and no transcript in the page. Home and About use a YouTube `iframe`. Media uses the `video` in item 1. None of the three has a `track`. Action: add a caption `track` or a transcript that matches the clip that is actually on that page.

5. **Medium.** About’s share address is the source file. `og:url` and the AboutPage `url` are `https://github.com/vandyparkes/capstone-project/blob/main/site/about.html`. No rendered address for the four pages is in the source. Action: set both to the published About URL after that address exists.

6. **Medium.** Module notes still describe the old folder and the old players. `Accessibility Conformance.md` and `Media Check.md` name `CSS Architecture Package/`. `Media and Typography Inventory/Media and Typography Inventory.md` says the four pages have no `iframe`. Home and About in `site/` each have one. Action: point those notes at `site/` and at the current Home and About embeds before the package is submitted.

## 3. Evidence already complete

These checks still match the files in `site/`.

### Module 1. Content inventory and site map

`planning-brief-starter/site-map-template.md`. The map is Home, Media, Services, and About.

`planning-brief-starter/acceptance-criteria-template.md`. Each page title includes `Bulletproof Personal Training`. The request form fields are name, email, and area of interest. Home and About each use a YouTube embed.

`planning-brief-starter/css-planning.md`. The same header and nav are on all four pages. The player stays on `media.html`.

### Module 2. CSS architecture

`site/css/main.css` loads reset, base, layout, components, utilities, states, overrides, then `print.css`. That order is the list in `CSS Architecture Package/architecture-notes.md`.

`CSS Architecture Package/README.md` points the pages at `../site/`.

`CSS Architecture Package/card-width-test.md` and `CSS Architecture Package/container-query-note.md`. `.card` in `site/css/components.css` has `container-type: inline-size`.

### Module 3. Layout systems

`Layout Risk and Breakpoint Inventory/Layout Risk and Breakpoint Inventory.md`. The pages still use the header, the Home hero, the card grids, the About video beside the bio, and the Services price table.

`site/css/states.css`. Under `prefers-reduced-motion: reduce`, the 1px press shift on buttons and nav is `none`.

`CSS Architecture Package/testing-evidence.md`. The narrow, medium, and wide notes for nav wrap, card columns, stacked price rows, and the About gallery. The font files are still 11,208 bytes and 11,364 bytes.

### Module 4. Media and typography

`Media and Typography Inventory/Media and Typography Inventory.md`. The four Training spaces photos, their `alt` text, figcaptions, sources, and licenses. Atkinson Hyperlegible 400 and 700, the fallback stack, and `fonts/OFL.txt`.

The squat player poster on `site/media.html` is still `images/video-placeholder.svg`, 167 bytes. `services.html` still has no `img`.

### Module 5. Accessibility

`Accessibility Conformance.md`, Contrast. Those pairs use the colors still set in `site/css/base.css`.

`Practice: Forms, Tables, Media, and Motion Check.md`. On `services.html`, `label for` matches `id` for `name`, `email`, and `interest`. A completed submit is `POST` to `services.html`. That check recorded `501` and `Unsupported method ('POST')`.

`services.html` still has one table. The caption is `Session type, access, price, and notes`. The column headers are Type, Access, Price, and Notes.

Each page still has `lang="en"`, one `header`, one `nav` with `aria-label="Main"`, one `main id="main"`, one `footer`, and `Skip to main content` pointing at `#main`.

### Module 6. Discoverability

`Metadata Inventory.md`, sections 2 and 3. The four titles and the four meta descriptions match `site/`.

`Discoverability and Structured Content.md`, section 2. Same titles and descriptions.

Section 3. The heading list and the nav links for Home, Media, Services, and About match the four files.

Section 4. No `link rel="canonical"`. No `meta name="robots"`. No `robots.txt`. No `sitemap.xml`.

Section 9. The notes record no search-rank claim, no index claim, and no price-in-search claim.

About `og:title` and `og:description` match the `title` and the meta description. The AboutPage `name` is `About the trainer`. The AboutPage `description` matches the meta description.
