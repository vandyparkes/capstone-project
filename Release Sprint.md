# Release sprint

Site files: `site/`.

Repository: https://github.com/vandyparkes/capstone-project

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
