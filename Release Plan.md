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

1. **High.** The session form opens on an error. `site/services.html` sets the email field to `not-an-email`, `aria-invalid="true"`, and `is-invalid` on its parent. `.field.is-invalid .field-error` is `display: block`, so `Enter a valid email we can reply to.` is on screen before a visitor types. Action: start that field empty, with `aria-invalid="false"` and without `is-invalid`.

2. **High.** A valid submit leaves the page. The form is `method="post"` and `action="#"`. The script does not listen for `submit`. `Discoverability and Structured Content.md` records the file server response `501` and `Unsupported method ('POST')`. The page has no confirmation text. Action: keep a valid submit on `services.html` and show a result on that page.

3. **Medium.** About’s share address is the source file. `og:url` and the AboutPage `url` are `https://github.com/vandyparkes/capstone-project/blob/main/site/about.html`. No rendered address for the four pages is in the source. Action: set both to the published About URL after that address exists.

4. **Medium.** Module notes still describe the old folder, the old players, and the old font stack. `Accessibility Conformance.md`, `Media Check.md`, `Metadata Inventory.md`, and `Discoverability and Structured Content.md` name `CSS Architecture Package/`. `Media and Typography Inventory/Media and Typography Inventory.md` says the four pages have no `iframe` and that the stack is `"Atkinson Hyperlegible", Arial, Helvetica, sans-serif`. Home, About, and Media in `site/` use YouTube `iframe` elements. `site/css/base.css` sets `--font-family` to `"Site Futura", Futura, "Atkinson Hyperlegible", Arial, Helvetica, sans-serif`. Action: point those notes at `site/`, at the current embeds, and at the current font stack before the package is submitted.

## 3. Evidence already complete

These checks still match the files in `site/`.

### Module 1. Content inventory and site map

`planning-brief-starter/site-map-template.md`. The map is Home, Media, Services, and About.

`planning-brief-starter/acceptance-criteria-template.md`. Each page title includes `Bulletproof Personal Training`. The request form fields are name, email, and area of interest. Home and About each use a YouTube embed. Media’s three beginner cards and `#player` each embed `https://www.youtube.com/embed/_sKBQYCTT2s`.

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

`Media and Typography Inventory/Media and Typography Inventory.md`. The four Training spaces photos, their `alt` text, figcaptions, sources, and licenses. `fonts/OFL.txt` is in `site/fonts/`. The two Atkinson files named in that inventory are still in `site/fonts/`.

`site/media.html` embeds `https://www.youtube.com/embed/_sKBQYCTT2s` on Squat setup, Hinge, Push-up path, and inside `#player`. The three advanced cards use `images/video-placeholder.svg` as an `img`. Each of those `img` elements has an `alt`. The file is 167 bytes, 1600 by 900. `services.html` still has no `img`.

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

## 4. Evidence still needed

### Published URL

No rendered address for the four pages is in the source. `Structured Data and Social Preview Check.md` records `200` for `CSS Architecture Package/about.html` and `CSS Architecture Package/images/home-gym-800.jpg`. The current About tags point at `site/about.html` and `site/images/home-gym-800.jpg`. Those two addresses have no recorded status. A rendered Home, Media, Services, and About URL has no recorded status.

### Validation

`Discoverability and Structured Content.md` records a Nu Html Checker upload and a Schema Markup Validator upload. Those uploads are the earlier files. Home and About each have one YouTube `iframe`. Media has four YouTube `iframe` elements and three `img` elements. No Nu result is recorded for the current four files. No Schema result is recorded for the current AboutPage `url`.

### Links

No link check is recorded for the current nav, Home `https://youtu.be/4S1SCnlqKHQ`, About `https://www.youtube.com/watch?v=rWTYOwgvwt8`, Media `https://youtu.be/_sKBQYCTT2s`, or `Open video` to `#player`.

### Performance

`CSS Architecture Package/testing-evidence.md` records no `iframe` and no YouTube host. Home now loads one YouTube embed. About now loads one YouTube embed. Media now loads four embeds of `https://www.youtube.com/embed/_sKBQYCTT2s` and `images/video-placeholder.svg` on the three advanced cards. No layout-shift score and no request list is recorded for those embeds.

### Compatibility

`CSS Architecture Package/architecture-notes.md` says Safari and Firefox still need a pass. The recorded browser checks name Chrome.

### Technical defense

This project has no technical defense note for the current Home, Media, Services, and About pages.

### Current media

`Media Check.md` describes a `video` with `controls` and no `src`. `#player` is an `iframe` with `title` `Squat setup` and `src` `https://www.youtube.com/embed/_sKBQYCTT2s`. The three beginner cards use that same `src`. No check is recorded for those `title` values, the Home iframe `title` `Bulletproof PT`, the About iframe `title` `Squat video (385lbs)`, or the `Watch on YouTube` links.

## 5. Scope decisions

This release stays on the four pages in `site/`. The items below stay out.

1. **Pages.** No fifth content page. `#player` stays a section on `media.html`. The root `index.html` only sends the browser to `site/`.

2. **Booking.** The request form on `services.html` is the booking path. No Calendly link, no Google Meet link, and no calendar page. `planning-brief-starter/site-map-template.md` lists those as an open risk. `planning-brief-starter/css-planning.md` says there is no live-calendar state.

3. **Accounts and payment.** No login and no payment. `planning-brief-starter/content-inventory-template.md` row C9 says no live payment or account login. The form fields stay name, email, and area of interest.

4. **Waiver.** C11 stays off the site until that legal text is reviewed. `css-planning.md` says no waiver until legal review.

5. **Testimonials.** C12 stays off Home. That row says testimonials are optional and need permission. Home has no testimonial block.

6. **Prices.** Each price cell stays `TBD after consultation`. C4 says to publish rates only after they are decided. No checkout.

7. **Media videos.** Squat setup, Hinge, Push-up path, and `#player` stay on `https://www.youtube.com/embed/_sKBQYCTT2s` until real training instructional videos are available. The three advanced cards stay labeled `Members only` and keep `images/video-placeholder.svg`. No member unlock and no extra tutorial page.

8. **Platform link.** `YouTube technique library` on About stays text. No URL for it is in `about.html`.

9. **Crawl files.** No `link rel="canonical"`, no `meta name="robots"`, no `robots.txt`, and no `sitemap.xml` on the four pages. `Discoverability and Structured Content.md` says those come after publication.

10. **Share tags.** Open Graph tags and the AboutPage JSON-LD stay on About. Home, Media, and Services have none.

11. **Print.** `site/css/main.css` loads `print.css` on every page. The sheet hides `.site-header nav`, `.button`, `.session-form`, and `.media-object__frame`. The price table rules stay in that sheet. Home, Media, and About have no second print file. `css-planning.md` says those pages do not need rich print.

## 6. Release plan

Before submission. The four pages stay in `site/`.

1. **Form.** On `site/services.html`, the email field starts empty, with `aria-invalid="false"` and without `is-invalid`. The script listens for `submit`. A valid submit stays on `services.html` and the result shows on that page.

2. **Notes.** Point `Accessibility Conformance.md`, `Media Check.md`, `Metadata Inventory.md`, `Discoverability and Structured Content.md`, and `Media and Typography Inventory/Media and Typography Inventory.md` at `site/`, the current YouTube `iframe` elements, and `--font-family` in `site/css/base.css`.

3. **Checks.** Nu Html Checker for the current four files. Schema Markup Validator for the current AboutPage `url`. Link check for the nav, Home `https://youtu.be/4S1SCnlqKHQ`, About `https://www.youtube.com/watch?v=rWTYOwgvwt8`, Media `https://youtu.be/_sKBQYCTT2s`, and `Open video` to `#player`. Request list for the Home embed, the About embed, the four Media embeds, and the three advanced-card `img` elements. Record the iframe `title` values and the `Watch on YouTube` links. Record Safari and Firefox for the four pages.

4. **Left in place.** The Media embeds stay on `https://www.youtube.com/embed/_sKBQYCTT2s` until real training instructional videos are available. `og:url` and the AboutPage `url` stay `https://github.com/vandyparkes/capstone-project/blob/main/site/about.html` until a published About address is in the source. No status is recorded for an address that is not in the source. No technical defense note until the checks in item 3 are recorded. Section 5 stays out.
