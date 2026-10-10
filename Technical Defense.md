# Technical defense

## What I built

Four pages in `site/`. Home, Media, Services, and About. Same header, nav, and footer on each. Semantic HTML and layered CSS. No framework. One small script on Services.

## Why it fits

The audience is beginners through advanced trainees who want online or in-person coaching. The three tasks are watch tutorials, read the trainer's background, and request a session.

- Watch. Media lists free beginner tutorials first. Advanced videos are labeled `Members only`. Nothing fakes an unlock.
- Background. About has the coaching approach, credentials, an intro video, and the Training spaces photos.
- Request. Services has session types, a price table, and a form with name, email, and area of interest. No health, payment, or waiver fields.

No login, payment, or live calendar. That matches the Planning Package brief.

## What I tested

`Release Sprint.md`, sections 1 to 6.

- Nu Html Checker on all four pages, 0 messages. CSS Validator on `main.css`.
- Lighthouse on the four published pages. Performance, Accessibility, and SEO 100. Best Practices 93 to 96, then 96 to 100 after the favicon.
- Nav and content links from a local server and the published pages.
- Services at 375, 768, 1280, and 200% zoom.
- Keyboard order and focus ring on Services.
- Media load timing and layout shift in Chrome.
- Titles, descriptions, Open Graph, and JSON-LD on the published pages.

## What I fixed

`Release Sprint.md`, section 7.

- The email field opened on an error. It now starts empty and valid.
- A valid submit left the page with a 501. It now stays on Services and shows `Form submitted.`
- About `og:url` and the AboutPage `url` named the GitHub source file. Both now name the published About page.
- Without JavaScript, the form posted and got a 405. It now uses `get` and reloads Services.
- No favicon. Every page logged a 404. `images/favicon.png` is now linked on all four pages.

## What remains limited

`Release Sprint.md`, sections 8 and 9.

- The form sends nothing. Without JavaScript, Services reloads with the fields in the address and no confirmation.
- The beginner cards and the player share one stand-in YouTube video.
- No captions or transcripts on the site.
- Prices are TBD. Advanced videos are placeholders.
- Chrome only. Safari and Firefox are not tested.
