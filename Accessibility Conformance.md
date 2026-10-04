# Accessibility conformance

Site files: `CSS Architecture Package/`. Open each page in a browser from that folder.

## Test scope

Four pages. Each one holds a check the others do not.

**Home** (`index.html`). Shared header, skip link, nav, `aria-current="page"`, footer, and heading outline. Two links use class `button`. One `video` with `controls`, poster `images/video-placeholder.svg`, no `src`, and a fallback link inside the `video`.

**Services** (`services.html`). The only form: Name, Email (`aria-invalid="true"`, `aria-describedby="email-error"`), Area of interest, and "Submit request." The only table: caption, `th scope="col"`, and `data-label` on each cell. `print.css` targets this page.

**Media** (`media.html`). Three "Open video" links to `#player`. One `video` with `controls`, the same poster, no `src`, `aria-label`, and `aria-describedby="player-text"`. Locked cards have no link and no button. One `aside`.

**About** (`about.html`). The only `img` elements. Four figures, each with `alt`, `srcset`, and a `figcaption`. One `video` with `controls`, the same poster, no `src`. One link uses `href="#"`.

Home, Services, and Media have no `img`. The photographs, alt text, and captions are on About.
