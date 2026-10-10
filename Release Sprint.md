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

### 1.1 Nu Html Checker, all four pages

Condition. Current `site/index.html`, `site/media.html`, `site/services.html`, and `site/about.html`, sent to `https://validator.w3.org/nu/` as `text/html`. Checker version 26.10.9.

Result. Home, 0 messages. Media, 0 messages. Services, 0 messages. About, 0 messages.

Issue. None.

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

Condition. `site/media.html` from `http://127.0.0.1:8765/`, three loads, Chrome Performance API. Lighthouse is in 5.1.

Result. First contentful paint 44, 52, and 48 ms. Layout shift 1 on the first load, 0 on the next two. The first shift was `body` moving from 8,8 to 0,0 at 20 ms. The four YouTube iframes took 270 to 805 ms each across the loads. All four use `https://www.youtube.com/embed/_sKBQYCTT2s` and all four have `loading="lazy"`. The two Atkinson font files were preloaded and showed `unloaded` in `document.fonts`.

Issue. The four iframes are the slowest items on the page. The layout shift of 1 did not repeat.

Fix. No edit. Release Plan section 5, item 7, keeps the four embeds on that URL until real training videos are available.

Retest. Not run. No file was edited.

### 5.1 Lighthouse

Condition. Lighthouse 12.8.2 CLI, headless Chrome. Published Home, Media, Services, and About at `https://vandyparkes.github.io/capstone-project/site/`. Mobile and desktop presets. Published Services was the version before 7.4.

Result.

| Page | Preset | Performance | Accessibility | Best Practices | SEO | FCP | LCP | TBT | CLS |
|---|---|---|---|---|---|---|---|---|---|
| Home | Mobile | 100 | 100 | 93 | 100 | 0.8 s | 1.1 s | 0 ms | 0 |
| Home | Desktop | 100 | 100 | 93 | 100 | 0.2 s | 0.3 s | 0 ms | 0 |
| Media | Mobile | 100 | 100 | 93 | 100 | 0.8 s | 0.9 s | 0 ms | 0 |
| Media | Desktop | 100 | 100 | 93 | 100 | 0.3 s | 0.4 s | 0 ms | 0 |
| Services | Mobile | 100 | 100 | 96 | 100 | 0.8 s | 0.9 s | 0 ms | 0 |
| Services | Desktop | 100 | 100 | 96 | 100 | 0.2 s | 0.2 s | 0 ms | 0 |
| About | Mobile | 100 | 100 | 93 | 100 | 0.8 s | 1.1 s | 0 ms | 0 |
| About | Desktop | 100 | 100 | 93 | 100 | 0.2 s | 0.3 s | 0 ms | 0 |

- Every page logs one console error: `https://vandyparkes.github.io/favicon.ico` returned 404.
- Home, Media, and About log a cookie issue from the YouTube embed and list a facade for the YouTube player.
- About lists properly sized images, 54 KiB on mobile, and next-gen formats, 89 KiB on mobile.
- Every page lists a short cache lifetime. GitHub Pages sets the cache headers.

Issue. The favicon 404 lowers Best Practices. The YouTube items come from the embed.

Fix. No edit.

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

### 7.4 Form without JavaScript

Condition. `site/services.html`, form sent without the script.

Result. The form was `method="post"` with `action="#"`. A POST to `services.html` returned 501 from `http://127.0.0.1:8765/` and 405 from GitHub Pages.

Issue. Required part 3. The request task depended on JavaScript.

Fix. The form is now `method="get"` with `action="services.html"`.

Retest. A GET to `services.html?name=A&email=a%40b.co&interest=Online+technique` returned 200 from `http://127.0.0.1:8765/` and from GitHub Pages. The `required` fields still block an empty submit in the browser. With the script, a valid submit still calls `preventDefault` and shows `Form submitted.`

## 8. Compatibility

Condition. Browser checks recorded in this repo. CSS features read from `site/css/`.

Result. Chrome is the only browser recorded. Safari and Firefox were not run.

- `@layer` with layered `@import` in `main.css`. A browser without cascade layers drops those imports and shows unstyled HTML.
- Card container query in `components.css` is inside `@supports (container-type: inline-size)`. Without it the badges stay stacked.
- Subgrid in `layout.css` is inside `@supports (grid-template-rows: subgrid)`. Without it the gallery stays in the auto-fill grid.
- Price table `@container (width < 48rem)` has no `@supports`. Without container queries the table stays a table at every width.
- About `@container (width > 64rem)` has no `@supports`. Without container queries the video stays above the bio.
- `aspect-ratio` holds the 16:9 frames and the 3:2 gallery tiles.

Issue. Safari and Firefox have no recorded result.

Fix. No edit.

Retest. Not run.

## 9. Known limitations

- The request form has no backend. With JavaScript, a valid submit shows `Form submitted.` and nothing is sent. Without JavaScript, the browser reloads `services.html` with the fields in the address and shows no confirmation.
- Squat setup, Hinge, Push-up path, and `#player` all embed `https://www.youtube.com/embed/_sKBQYCTT2s` until real training videos exist.
- No `track` and no transcript on any page. Captions depend on the YouTube player.
- The three advanced cards are placeholders. There is no member access.
- Every price is `TBD after consultation`.
- `YouTube technique library` on About is text with no link.
- CSS Validator reports 8 errors on `main.css` for `@import` after `@layer`. Cascade Layers allows a `@layer` statement before `@import`. The file was left as is.
- Safari and Firefox are not tested. See section 8.
- No favicon. Every page logs a 404 for `favicon.ico`. See 5.1.
