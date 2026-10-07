# Discoverability and structured content

Site files: `CSS Architecture Package/`. Headings and links below match `Accessibility Conformance.md`.

## 1. Metadata inventory

Checked `index.html`, `media.html`, `services.html`, and `about.html` in `CSS Architecture Package/`. Each head has one `title` and one `meta name="description"`. None has `link rel="canonical"`.

### Home (`index.html`)

**Page purpose.** Name the company and send the reader to tutorials or a session request.

**User task.** Read the company name, then open tutorials or request a private online or in-home session.

**Title.** `Home | Bulletproof Personal Training`

**Meta description.** `Bulletproof Personal Training: beginner and advanced technique videos plus private session requests.`

**Visible content.** The `h1` is `Bulletproof Personal Training`. The intro says `Learn beginner and advanced lifting technique from training videos, then request a private online or in-home session.` The links under it are `Watch tutorials` and `Request a session`. Later headings are `What you can do here` and `Start with these pages`. The description uses the same two tasks as that intro.

**Canonical decision.** No `link rel="canonical"`. The page is one file, `index.html`. No second address is in the source. No `og:url` is on this page. A canonical link names one address when the same page is published at more than one address. This file does not have that.

### Media (`media.html`)

**Page purpose.** List the free beginner tutorials and keep the advanced clips labeled for members.

**User task.** Watch the free beginner tutorials. Advanced clips stay labeled for members.

**Title.** `Media | Bulletproof Personal Training`

**Meta description.** `Free beginner tutorials and locked advanced training videos from Bulletproof Personal Training.`

**Visible content.** The `h1` is `Media`. The intro says `Watch free beginner tutorials. Advanced videos stay labeled for members and are not shown as unlock buttons.` Headings under that are `Beginner tutorials`, `Advanced and locked tutorials`, `Training note`, and `Player: Squat setup`. Beginner cards: `Squat setup`, `Hinge`, `Push-up path`. Advanced cards: `Paused squat loading`, `Single-leg hinge`, `Press variations`. The description names those two groups.

**Canonical decision.** No `link rel="canonical"`. The page is one file, `media.html`. No second address is in the source. No `og:url` is on this page. A canonical link names one address when the same page is published at more than one address. This file does not have that.

### Services (`services.html`)

**Page purpose.** Show session types and prices, then take a session request.

**User task.** Compare session types and prices, then request a session.

**Title.** `Services | Bulletproof Personal Training`

**Meta description.** `Session types, pricing, and a request form for Bulletproof Personal Training.`

**Visible content.** The `h1` is `Services`. The intro says `Compare session types, then request coaching.` Headings are `Session types`, `Pricing`, and `Request a session`. Session cards: `Online technique`, `In-home training`, `Advanced review`. Each price cell says `TBD after consultation`. The form fields are Name, Email, and Area of interest, with `Submit request`. The description names the session types, the pricing heading, and that form.

**Canonical decision.** No `link rel="canonical"`. The page is one file, `services.html`. No second address is in the source. No `og:url` is on this page. A canonical link names one address when the same page is published at more than one address. This file does not have that.

### About (`about.html`)

**Page purpose.** Show the trainer background, the credentials list, the platform list, and the training-space photos.

**User task.** Read the trainer background, the credentials, the platform list, and the training-space photos.

**Title.** `About | Bulletproof Personal Training`

**Meta description.** `Trainer background, credentials, and platform list for Bulletproof Personal Training.`

**Visible content.** The `h1` is `About the trainer`. `Coaching approach` has the paragraph that starts `Bulletproof PT teaches simple cues first, then adds load.` Under it, `Credentials` lists `Certified personal trainer`, `In-home and online coaching`, and `Beginner through advanced technique reviews`. `Other platforms` lists `YouTube technique library` as text and `Request a private session` as a link. Also on the page: `Beginner and advanced coaching` and `Training spaces` (four photos). The description names the coaching paragraph, the credentials list, and `Other platforms`. It does not name `Training spaces`.

**Canonical decision.** No `link rel="canonical"`. The page is one file, `about.html`. `og:url` is on this page. That tag is not a canonical link. A canonical link names one address when the same page is published at more than one address. This file does not have that.

## 2. Titles and descriptions

Each page has one `title` and one `meta name="description"`. The four titles do not match.

**Home** (`index.html`). `Home | Bulletproof Personal Training`. The description names beginner and advanced technique videos and private session requests. The intro says the same thing.

**Media** (`media.html`). `Media | Bulletproof Personal Training`. The description names free beginner tutorials and locked advanced training videos. The intro says advanced videos stay labeled for members.

**Services** (`services.html`). `Services | Bulletproof Personal Training`. The description names session types, pricing, and a request form. Those three are on the page.

**About** (`about.html`). `About | Bulletproof Personal Training`. The description says `Trainer background, credentials, and platform list for Bulletproof Personal Training.` The page has the coaching paragraph, the credentials list, and the heading `Other platforms`. `YouTube technique library` is text.

## 3. Semantic headings and crawlable links

Each page has one `h1`. The next headings are `h2`, then `h3`. No level is skipped. The outline matches `Accessibility Conformance.md`. Task links are `a` elements with an `href`.

The same nav is on each page: `Bulletproof PT` (`index.html`), `Home` (`index.html`), `Media` (`media.html`), `Services` (`services.html`), `About` (`about.html`). `Skip to main content` points at `#main`.

**Home** (`index.html`). `h1` Bulletproof Personal Training. `h2` What you can do here. `h3` Watch technique. `h3` Request coaching. `h2` Start with these pages. `h3` Media. `h3` Services. `h3` About. `Watch tutorials` goes to `media.html`, under the intro and under Watch technique. `Request a session` goes to `services.html`, under the intro and under Request coaching. `Open Media`, `Open Services`, and `Open About` go to those pages. The footer `Services` link goes to `services.html`.

**Media** (`media.html`). `h1` Media. `h2` Beginner tutorials. `h3` Squat setup. `h3` Hinge. `h3` Push-up path. `h2` Advanced and locked tutorials. `h3` Paused squat loading. `h3` Single-leg hinge. `h3` Press variations. `h2` Training note. `h2` Player: Squat setup. `Open video` is under Squat setup and goes to `#player`. Hinge and Push-up path have no `a`. Single-leg hinge and Press variations have no `a`. Paused squat loading links `Request a session` to `services.html`. `Back to tutorials` goes to `media.html`. The footer `Services` link goes to `services.html`.

**Services** (`services.html`). `h1` Services. `h2` Session types. `h3` Online technique. `h3` In-home training. `h3` Advanced review. `h2` Pricing. `h2` Request a session. `Request a session` goes to `#request`. The footer `Media` link goes to `media.html`.

**About** (`about.html`). `h1` About the trainer. `h2` Coaching approach. `h3` Credentials. `h2` Beginner and advanced coaching. `h3` Foundations. `h3` Loaded variations. `h2` Other platforms. `h2` Training spaces. `Watch tutorials` under the figcaption goes to `media.html`. `Request a private session` goes to `services.html`. `YouTube technique library` is text. No URL for it is in the page. The footer `Media` link goes to `media.html`.

Home and About also have `Watch tutorials` (`media.html`) inside the `video`, with `tabindex="-1"`. Media has `Back to tutorials` (`media.html`) inside the `video`, with `tabindex="-1"`.

## 4. Canonical, robots, and sitemap notes

Checked `index.html`, `media.html`, `services.html`, and `about.html`. No `robots.txt`. No `sitemap.xml`.

**Canonical.** After publication. Not now. No `link rel="canonical"` is in the four files. Each page is one file in `CSS Architecture Package/`. The source has no second address for the same page. About has `og:url`. That tag is not a canonical link. A canonical link names one address after the same page is published at more than one address.

**Robots.** Not now. After publication, only if the host needs a fetch rule. No `meta name="robots"` is in the four files. No `robots.txt` is in the project. These pages are files in a folder. Nothing in the files hides Home, Media, Services, or About.

**Sitemap.** After publication. Not now. No `sitemap.xml` is in the project. A sitemap lists published addresses. The four pages are `index.html`, `media.html`, `services.html`, and `about.html`. No published address for that set is in the source.

## 6. Structured data

About (`about.html`) has one `script type="application/ld+json"`. The type is `AboutPage`. `name` is the heading `About the trainer`. `description` matches `meta name="description"`. `url` matches `og:url`.

The current nav item is About. The page shows the coaching paragraph, the credentials list, the heading `Other platforms`, and the Training spaces photos.

Checked `about.html` in the [Schema Markup Validator](https://validator.schema.org/). One `AboutPage` node. 0 errors. 0 warnings.

Home, Media, and Services have no `script type="application/ld+json"`.

**Home.** `index.html` has no address and no site URL. The logo is the text `Bulletproof PT`.

**Media.** The `video` has no `src`, no `track`, and no transcript. The poster is one gray rectangle.

**Services.** Each price cell says `TBD after consultation`. A filled submit leaves the form. The file server returns `Error code: 501` and `Unsupported method ('POST')`. The form has no confirmation text.

The credentials list stays text. The page does not name a certifying body. `YouTube technique library` stays text. No URL for it is in the page.

## 5. Social metadata

Shareable page: About (`about.html`). Home, Media, and Services have no `og:` tags.

**Title.** `og:title` is `About | Bulletproof Personal Training`. It matches the `title`.

**Description.** `og:description` is `Trainer background, credentials, and platform list for Bulletproof Personal Training.` It matches `meta name="description"`. The page shows the coaching paragraph, the credentials list, and the heading `Other platforms`.

**URL.** `og:url` is `https://github.com/vandyparkes/capstone-project/blob/main/CSS%20Architecture%20Package/about.html`.

**Type.** `og:type` is `website`.

**Image.** `og:image` is `images/home-gym-800.jpg` on the Training spaces row. The figcaption is `Home gym coaching`. `og:image:alt` matches the `img` alt: `Trainer in a grey shirt squatting with a loaded barbell in a garage.` `og:image:width` is `800`. `og:image:height` is `533`. The file is 800 by 533.

## 7. Image discoverability

Important images are the four photos under `Training spaces` on About, and `images/video-placeholder.svg` on Home, About, and Media. Services has no `img` and no poster. `images/card-two-widths.png` is not used on those pages. The logo is the text `Bulletproof PT`.

Each About photo is an `img` in a `figure`, under the heading `Training spaces`. The `alt` describes the photo. The `figcaption` is the role of that photo on the page. `width` and `height` are `800` and `533`. The `srcset` file is the same photo at 480 by 320.

**Home gym.** Files: `images/home-gym-800.jpg`, `images/home-gym-480.jpg`. Alt: `Trainer in a grey shirt squatting with a loaded barbell in a garage.` Caption: `Home gym coaching`. 800 by 533, and 480 by 320. On About, this is the in-home training photo. It is also `og:image`.

**Online sessions.** Files: `images/online-800.jpg`, `images/online-480.jpg`. Alt: `Open laptop on a wooden table beside a notebook, a pen, and a phone.` Caption: `Online sessions`. 800 by 533, and 480 by 320. On About, this sits with the online coaching text.

**Small-space setup.** Files: `images/small-space-800.jpg`, `images/small-space-480.jpg`. Alt: `Two adjustable dumbbells and loose plates on a gray floor.` Caption: `Small-space setup`. 800 by 533, and 480 by 320. On About, this sits with the in-home coaching text.

**Session notes.** Files: `images/notes-800.jpg`, `images/notes-480.jpg`. Alt: `Small blue spiral notepad next to a one-euro coin.` Caption: `Session notes`. 800 by 533, and 480 by 320. On About, this sits with the session text under `Training spaces`.

**Video poster.** File: `images/video-placeholder.svg`. 1600 by 900. One rectangle, fill `#d4d0c8`. The `svg` is `aria-hidden="true"`. No `alt`. The poster attribute takes one URL. Home caption: `Highlight video placeholder`, under the heading `Bulletproof Personal Training`. About caption: `Trainer intro video placeholder`, beside the heading `Coaching approach`. Media has no caption on that file. The nearby heading is `Player: Squat setup`. The nearby text is `Keep the whole foot on the floor, brace before you sit, and push through the heel on the way up.` The file does not show the highlight, the trainer, or the squat.

## 8. Validation evidence

Source check of `index.html`, `media.html`, `services.html`, and `about.html`.

Each file has one `title` and one `meta name="description"`. The four titles do not match. No `link rel="canonical"`. No `meta name="robots"`.

About `og:title` matches the `title`. About `og:description` matches the meta description. About has one JSON-LD script. `name` is `About the trainer`. `description` matches the meta description. `url` matches `og:url`. Home, Media, and Services have no `og:` tags and no JSON-LD script.

[W3C Nu Html Checker](https://validator.w3.org/nu/). Document upload.

- Home: 0 messages.
- Services: 0 messages.
- About: 0 messages.
- Media: 1 info. Line 96. `The document is not mappable to XML 1.0 due to two consecutive hyphens in a comment.` The comment contains `.container--media`.

[Schema Markup Validator](https://validator.schema.org/). Document upload.

- Home: 0 objects.
- Media: 0 objects.
- Services: 0 objects.
- About: 1 `AboutPage`. 0 errors. 0 warnings.

## 9. Ranking-claim limits

**Search rank.** No claim that the titles, descriptions, Open Graph tags, or the About `AboutPage` JSON-LD set a search rank. The checks were the page source, the W3C Nu Html Checker, and the Schema Markup Validator. No search index was checked.

**Index status.** No claim that Home, Media, Services, or About are in a search index. No `link rel="canonical"`. No `robots.txt`. No `sitemap.xml`. No published address for the four pages is in the source.

**Video results.** No claim that the Media player appears in video search. The `video` has no `src`, no `track`, and no transcript. `YouTube technique library` is text. No URL for it is in the page.

**Prices in search.** No claim that the session rates appear as prices in search. Each price cell says `TBD after consultation`. Services has no JSON-LD.
