# AI disclosure

I used Grok on X only for organization, token names, and refactoring options.

**Purpose.** Keep the CSS consistent: one set of tokens, a clear file order, and shorter names instead of one-off selectors.

**Output considered.** A layer order (reset, base, layout, components, utilities, states, overrides); role-based tokens (`--color-accent`, `--space-8` through `--space-48`, `--radius`, `--focus-color`); and refactor options such as one `.card` pattern and job-based class names. I kept what matched the plan. I chose the values and applied the CSS myself.

**Verification.** I checked Home, About, Media, and Services in Chrome at about 375px, 768px, and a wide window, plus 200% zoom. Nav wraps with no sideways overlap. Cards and the About video/bio stack on a small screen. Focus, the Services form error state, reduced motion, and Services print preview still work. The later checks are in `testing-evidence.md`.

**What changed.** Repeated hex values became tokens. Long selectors became layers and short classes.
