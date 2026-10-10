# Release sprint

Site files: `site/`.

Repository: https://github.com/vandyparkes/capstone-project

## 1. Validation

Condition. Nu Html Checker upload of `site/services.html` and `site/media.html`. CSS Validator upload of `site/css/main.css`, CSS level 3.

Result. Services, 0 messages. Media, 0 messages. `main.css`, 8 errors, lines 5–12: `@import` after the `@layer` line.

Issue. `main.css` line 3 is the `@layer` list.

Fix. No edit.

Retest. Not run. No file was edited.
