# Media check

Object: the Squat setup player on `CSS Architecture Package/media.html`.

## 1. Does the media have a clear purpose on the page?

Yes. The page heading is Media. The intro says "Watch free beginner tutorials." The player heading is "Player: Squat setup." The Squat setup card says "Foot stance, brace, and a controlled descent." and links to `#player` with "Open video." Under the player: "Keep the whole foot on the floor, brace before you sit, and push through the heel on the way up."

The `video` has no `src`. The demo does not play.

Hinge pattern and Push-up path also link to `#player`. The heading there stays "Player: Squat setup."

## 2. Does audio or video have captions, transcripts, or another appropriate equivalent?

No. There is no `audio`. The `video` has no `track`. There is no transcript.

The Squat setup card says "Foot stance, brace, and a controlled descent." Under the player: "Keep the whole foot on the floor, brace before you sit, and push through the heel on the way up." The card shows "8:12." That line uses `text-caption`. It is the duration.

## 3. Are controls visible, keyboard reachable, and understandable?

Chrome. The `video` has `controls`. The bar shows play, 0:00, mute, fullscreen, and a menu.

`tabIndex` is 0. The video can take focus. The accessible name is "Squat setup video placeholder."

There is no `src`. The time stays at 0:00.

## 4. Does motion pause, stop, or respect reduced-motion preferences where needed?

The `video` has no `autoplay` and no `src`. Nothing plays. The time stays at 0:00.

`css/states.css` uses `prefers-reduced-motion: reduce` on `.button:active` and `.nav-list a:active`. It sets `transform` to `none`. That rule does not name `video`.

`testing-evidence.md` records that preference on. The 1px press shift on buttons and nav is off.

## 5. Does an iframe or embed have a meaningful title?

No. `media.html` has no `iframe` and no `embed`. The player is a `video`. There is no `title` on an embed.

## 6. Is there a fallback link or alternate path if the external embed fails?

No external embed. No link to a hosted clip.

The `video` poster is `images/video-placeholder.svg`. Under the player: "Keep the whole foot on the floor, brace before you sit, and push through the heel on the way up."

"Back to tutorials" links to `media.html`.

Print CSS hides `.media-object__frame`.

## 7. Does the media create a performance, privacy, or layout-shift risk?

No external media URL. The page does not load a third-party player.

`testing-evidence.md` records a layout shift score of 0 for Media. `.media-object__frame` uses `aspect-ratio: 16 / 9` before the poster shows. On Media that frame was 864 by 486. The poster is `images/video-placeholder.svg`, 1600 by 900, the same ratio. The poster does not push the text under it. There is no video file.
