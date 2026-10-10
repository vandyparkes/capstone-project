# Release sprint

Site files: `site/`.

Repository: https://github.com/vandyparkes/capstone-project

Published pages: https://vandyparkes.github.io/capstone-project/site/. `index.html`, `media.html`, `services.html`, and `about.html` each returned 200.

## 1. Validation

Condition. Nu Html Checker upload of `site/services.html` and `site/media.html`. CSS Validator upload of `site/css/main.css`, CSS level 3.

Result. Services, 0 messages. Media, 0 messages. `main.css`, 8 errors, lines 5–12: `@import` after the `@layer` line.

Issue. `main.css` line 3 is the `@layer` list.

Fix. No edit.

Retest. Not run. No file was edited.

## 2. Links

Condition. Nav on each page: Home `index.html`, Media `media.html`, Services `services.html`, About `about.html`. Five content links: Media “Open video” `#player`, Services “Request a session” `#request`, Home “Watch on YouTube” `https://youtu.be/4S1SCnlqKHQ`, About “Watch on YouTube” `https://www.youtube.com/watch?v=rWTYOwgvwt8`, Media “Watch on YouTube” `https://youtu.be/_sKBQYCTT2s`.

Result. From `http://127.0.0.1:8765/`, the four nav files each returned 200. `#player` is on `media.html`. `#request` is on `services.html`. The Home and Media YouTube links returned 303, then 200. The About YouTube link returned 200.

Issue. None.

Fix. No edit.

Retest. Not run. No file was edited.

## 3. Width and zoom

Condition. `site/services.html` at 375, 768, 1280, and 640. 640 is a 1280 window at 200%.

Result. No sideways scroll at those four widths. At 375 the header wraps and the three cards are one column. At 768 and 640 the header is one row and the cards sit on two rows. At 1280 the header is one row, the cards are one row, and the price table is a table. At 375, 768, and 640 the price rows are stacked. The name label and the email error stay on one line.

Issue. None.

Fix. No edit.

Retest. Not run. No file was edited.

## 4. Keyboard and focus

Condition. `site/services.html` at 1280. Tab order read from the DOM. Focus ring read with `:focus-visible` forced on the skip link, logo, Home, current nav link, “Request a session”, Email, and “Submit request”. A scripted Tab key did not move focus in this browser.

Result. 12 stops, in order: Skip to main content, Bulletproof PT, Home, Media, Services, About, Request a session, Name, Email, Area of interest, Submit request, footer Media. No `tabindex` above 0. `main` has `tabindex="-1"`. Each forced stop showed `3px solid rgb(155, 28, 28)`, offset 3px. The current nav link also showed underline.

Issue. None.

Fix. No edit.

Retest. Not run. No file was edited.

## 5. Performance

Condition. `site/media.html` from `http://127.0.0.1:8765/`, three loads, Chrome Performance API. Lighthouse was not run. Node is not installed.

Result. First contentful paint 44, 52, and 48 ms. Layout shift 1 on the first load, 0 on the next two. The first shift was `body` moving from 8,8 to 0,0 at 20 ms. The four YouTube iframes took 270 to 805 ms each across the loads. All four use `https://www.youtube.com/embed/_sKBQYCTT2s` and all four have `loading="lazy"`. The two Atkinson font files were preloaded and showed `unloaded` in `document.fonts`.

Issue. The four iframes are the slowest items on the page. The layout shift of 1 did not repeat.

Fix. No edit. Release Plan section 5, item 7, keeps the four embeds on that URL until real training videos are available.

Retest. Not run. No file was edited.

## 6. Metadata

Condition. Published pages at `https://vandyparkes.github.io/capstone-project/site/`: `index.html`, `media.html`, `services.html`, `about.html`. That address is the homepage field of the repository. Each page was fetched and its `title`, `meta name="description"`, `og:` tags, JSON-LD, `lang`, `viewport`, `link rel="canonical"`, and `meta name="robots"` were read.

Result. Each page returned 200 and matches the file in `site/`. Titles and descriptions match the Release Plan. Each page has `lang="en"` and a `viewport`. No page has a canonical or robots tag. Home, Media, and Services have no `og:` tags and no JSON-LD. About has `og:title`, `og:description`, `og:url`, `og:type`, `og:image`, `og:image:alt`, and the AboutPage JSON-LD. `og:url` and the AboutPage `url` are `https://github.com/vandyparkes/capstone-project/blob/main/site/about.html`. That address returned 503 on three requests. `og:image` returned 200 as `image/jpeg`. The published About page returned 200.

Issue. `og:url` and the AboutPage `url` name the source file, not the published About page.

Fix. No edit in this check.

Retest. Not run. No file was edited.

## 7. Fixes

### 7.1 Email field opens on an error

Condition. `site/services.html`, page load.

Result. The email field had `value="not-an-email"`, `aria-invalid="true"`, and `is-invalid` on its parent. `Enter a valid email we can reply to.` showed before any typing.

Issue. Release Plan, section 2, item 1.

Fix. The field starts empty, with `aria-invalid="false"` and no `is-invalid`.

Retest. On load the error is `display: none` and `aria-invalid` is `false`. An empty submit shows the name, email, and area errors.

### 7.2 A valid submit leaves the page

Condition. `site/services.html`, form with name, email, and area filled.

Result. The form was `method="post"` with `action="#"` and the script had no `submit` listener. The earlier check recorded `501` and `Unsupported method ('POST')`.

Issue. Release Plan, section 2, item 2.

Fix. A `submit` listener calls `preventDefault` and writes `Form submitted.` into `output#form-result`. `components.css` adds `.form-result:not(:empty)` with `display: block` and a 16px top margin.

Retest. A valid submit stays on `/services.html` and the text shows 16px under the form. An empty submit shows 3 errors and no text. The page height before submit is 1476, the same as before the edit. Nu Html Checker, 0 messages. CSS Validator on `components.css`, the same 4 errors as in section 1.

### 7.3 About share address names the source file

Condition. `site/about.html`.

Result. `og:url` and the AboutPage `url` were `https://github.com/vandyparkes/capstone-project/blob/main/site/about.html`.

Issue. Section 6.

Fix. Both are now `https://vandyparkes.github.io/capstone-project/site/about.html`.

Retest. The two values match. The published About page returned 200. Nu Html Checker, 0 messages. The JSON-LD parses.
