# Required parts

## 1. Published site

https://vandyparkes.github.io/capstone-project/site/

Home `index.html`, Media `media.html`, Services `services.html`, About `about.html`. Each returned 200. `Release Sprint.md`, section 6.

## 2. Repository

https://github.com/vandyparkes/capstone-project

- `README.md`. Published URL, file layout, evidence list.
- `site/`. The four pages, `css/`, `fonts/`, `images/`.
- `.gitignore`. `.DS_Store`, `.Rhistory`, `.zip`, and Premiere files are not tracked.

## 3. Production website

- `site/index.html`, `site/media.html`, `site/services.html`, `site/about.html`. Scope: `Release Plan.md`, sections 1 and 5.
- Semantic HTML: one `header`, `nav`, `main`, and `footer` per page. Skip link to `#main`.
- CSS: `site/css/main.css` loads reset, base, layout, components, utilities, states, overrides, then print.
- No JavaScript-dependent core task. The Services form sends with `get` and reloads Services without the script. `Release Sprint.md`, section 7.4.

## 4. Planning evidence

- Planning package: `Planning Brief/Planning Package.pdf`.
- Content architecture: `Planning Brief/content-inventory-template.md`, `Planning Brief/site-map-template.md`.
- Responsive wireframes and annotations: `Planning Brief/Planning Package.pdf`, `Planning Brief/css-planning.md`.
- Acceptance criteria: `Planning Brief/acceptance-criteria-template.md`.

## 5. Build evidence, Modules 2–6

Modules 2–6 were recorded against `CSS Architecture Package/` before the pages moved to `site/`. Current results are in `Release Sprint.md`.

| Module | Files |
|---|---|
| 2. CSS architecture | `CSS Architecture Package/architecture-notes.md`, `refactoring-notes.md`, `card-width-test.md`, `container-query-note.md`, `testing-evidence.md`, `Planning Package CSS Inventory.md` |
| 3. Responsive layout | `Layout Risk and Breakpoint Inventory.md` |
| 4. Media and typography | `Media and Typography Inventory.md`, `Media Check.md` |
| 5. Accessibility | `Accessibility Test Plan.md`, `Accessibility Conformance.md`, `Practice: Forms, Tables, Media, and Motion Check.md` |
| 6. Discoverability | `Metadata Inventory.md`, `Discoverability and Structured Content.md`, `Structured Data and Social Preview Check.md` |

## 6. Release evidence

`Release Sprint.md`.

| Part | Section |
|---|---|
| Validation | 1, 1.1 |
| Broken-link checks | 2 |
| Responsive regression checks | 3 |
| Accessibility spot checks | 4 |
| Performance diagnostic | 5, 5.1 |
| Metadata on the published pages | 6 |
| Fixes and retests | 7 |
| Compatibility notes | 8 |
| Known limitations | 9 |

## 7. Technical defense

`Technical Defense.md`. What was built, why it fits the audience and task, what was tested, what was fixed, and what remains limited.

## Rubric

| Criterion | Points | Files |
|---|---|---|
| Capstone scope, content, and user task fit | 60 | `site/`, `Release Plan.md` sections 1 and 5, `Technical Defense.md` |
| HTML/CSS architecture and implementation quality | 80 | `site/`, `CSS Architecture Package/`, `Layout Risk and Breakpoint Inventory.md` |
| Responsive media, typography, accessibility, and discoverability | 90 | Module 4–6 files above |
| Release quality and testing evidence | 80 | `Release Sprint.md` |
| Documentation and technical defense | 60 | `README.md`, `Release Plan.md`, `Release Sprint.md`, `Technical Defense.md` |
| AI transparency and source integrity | 30 | `CSS Architecture Package/ai-disclosure.md`. Image sources and licenses: `Media and Typography Inventory.md`, `site/fonts/OFL.txt` |
