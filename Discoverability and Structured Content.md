# Discoverability and structured content

Site files: `CSS Architecture Package/`. Headings and links below match `Accessibility Conformance.md`.

## 1. Metadata inventory

### Home (`index.html`)

**Page purpose.** Name the company and send the reader to tutorials or a session request.

**Title.** `Home | Bulletproof Personal Training`

**Meta description.** `Bulletproof Personal Training: beginner and advanced technique videos plus private session requests.`

**Canonical decision.** No `link rel="canonical"` in the file. The page is `index.html`. The source has no second address for it. A canonical link applies after this file is published at one address. It does not apply now.

**Primary heading.** `Bulletproof Personal Training`

**User task.** Read the company name, then open tutorials or request a private online or in-home session.

### Media (`media.html`)

**Page purpose.** List the free beginner tutorials and keep the advanced clips labeled for members.

**Title.** `Media | Bulletproof Personal Training`

**Meta description.** `Free beginner tutorials and locked advanced training videos from Bulletproof Personal Training.`

**Canonical decision.** No `link rel="canonical"` in the file. The page is `media.html`. The source has no second address for it. A canonical link applies after this file is published at one address. It does not apply now.

**Primary heading.** `Media`

**User task.** Watch the free beginner tutorials. Advanced clips stay labeled for members.

### Services (`services.html`)

**Page purpose.** Show session types and prices, then take a session request.

**Title.** `Services | Bulletproof Personal Training`

**Meta description.** `Session types, pricing, and a request form for Bulletproof Personal Training.`

**Canonical decision.** No `link rel="canonical"` in the file. The page is `services.html`. The source has no second address for it. A canonical link applies after this file is published at one address. It does not apply now.

**Primary heading.** `Services`

**User task.** Compare session types and prices, then request a session.

### About (`about.html`)

**Page purpose.** Show the trainer background, the credentials list, the platform list, and the training-space photos.

**Title.** `About | Bulletproof Personal Training`

**Meta description.** `Trainer background, credentials, and platform list for Bulletproof Personal Training.`

**Canonical decision.** No `link rel="canonical"` in the file. The page is `about.html`. `og:url` is on this page. That tag is not a canonical link. A canonical link applies after this file is published at one address. It does not apply now.

**Primary heading.** `About the trainer`

**User task.** Read the trainer background, credentials, and platform list.

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

## 5. Social metadata

Shareable page: About (`about.html`). Home, Media, and Services have no `og:` tags.

**Title.** `og:title` is `About | Bulletproof Personal Training`. It matches the `title`.

**Description.** `og:description` is `Trainer background, credentials, and platform list for Bulletproof Personal Training.` It matches `meta name="description"`. The page shows the coaching paragraph, the credentials list, and the heading `Other platforms`.

**URL.** `og:url` is `https://github.com/vandyparkes/capstone-project/blob/main/CSS%20Architecture%20Package/about.html`.

**Type.** `og:type` is `website`.

**Image.** `og:image` is `images/home-gym-800.jpg` on the Training spaces row. The figcaption is `Home gym coaching`. `og:image:alt` matches the `img` alt: `Trainer in a grey shirt squatting with a loaded barbell in a garage.` `og:image:width` is `800`. `og:image:height` is `533`. The file is 800 by 533.
