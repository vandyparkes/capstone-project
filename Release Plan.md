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
