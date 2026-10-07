# AI disclosure

I used Grok on X for organization, token names, and refactoring options. I used Grok again to draft alternatives and organize the metadata inventory.

**Purpose.** Keep the CSS consistent: one set of tokens, a clear file order, and shorter names instead of one-off selectors.

**Output considered.** A layer order (reset, base, layout, components, utilities, states, overrides); role-based tokens (`--color-accent`, `--space-8` through `--space-48`, `--radius`, `--focus-color`); and refactor options such as one `.card` pattern and job-based class names. I kept what matched the plan. I chose the values and applied the CSS myself.

**Verification.** I checked Home, About, Media, and Services in Chrome at about 375px, 768px, and a wide window, plus 200% zoom. Nav wraps with no sideways overlap. Cards and the About video/bio stack on a small screen. Focus, the Services form error state, reduced motion, and Services print preview still work. The later checks are in `testing-evidence.md`.

**What changed.** Repeated hex values became tokens. Long selectors became layers and short classes.

**Inventory.** Grok drafted two ways to state the canonical decision and draft lines for the visible text on each page. I used that to organize section 1 of `Discoverability and Structured Content.md`.

**Purpose.** Tie Home, Media, Services, and About to purpose, user task, title, description, visible content, and the canonical decision.

**Output considered.** Draft visible-content lines, and a canonical line that names one address when the same page is published at more than one address. I kept the lines that match the four HTML files. I applied the section myself.

**Verification.** I compared section 1 with the `title`, `meta name="description"`, headings, and intro text in `index.html`, `media.html`, `services.html`, and `about.html`. The HTML files were not changed.
