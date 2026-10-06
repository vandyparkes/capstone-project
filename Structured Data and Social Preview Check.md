# Structured Data and Social Preview Check

Page: About (`CSS Architecture Package/about.html`).

## 1. Open Graph

`og:title` matches `<title>About | Bulletproof Personal Training</title>`.

`og:description` matches `meta name="description"`. The page shows the trainer background, the credentials list, and the platform list.

`og:url` is the About file on `main`. Checked 6 Oct 2026. That URL returned `200` and `text/html`.

`og:type` is `website`.

`og:image` is the Training spaces photo captioned `Home gym coaching` (`images/home-gym-800.jpg`). Visible alt: `Man in a gray shirt squatting with a loaded barbell in a garage.` Checked 6 Oct 2026. That URL returned `200` and `image/jpeg`.

```html
<meta property="og:title" content="About | Bulletproof Personal Training">
<meta property="og:description" content="Trainer background, credentials, and platform links for Bulletproof Personal Training.">
<meta property="og:url" content="https://github.com/vandyparkes/capstone-project/blob/main/CSS%20Architecture%20Package/about.html">
<meta property="og:type" content="website">
<meta property="og:image" content="https://raw.githubusercontent.com/vandyparkes/capstone-project/main/CSS%20Architecture%20Package/images/home-gym-800.jpg">
```

## 2. Structured-data type

Type: `AboutPage`.

The heading on the page is `About the trainer`. The title is `About | Bulletproof Personal Training`. The current nav item is About. The page shows the coaching approach, the credentials list, beginner and advanced coaching, the platform list, and the Training spaces photos.

## 3. JSON-LD

`name` is the heading `About the trainer`.

`description` matches `meta name="description"`. The page shows the trainer background, the credentials list, and the platform list.

`url` is the same About file on `main` as `og:url`.

```html
<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "AboutPage",
    "name": "About the trainer",
    "description": "Trainer background, credentials, and platform links for Bulletproof Personal Training.",
    "url": "https://github.com/vandyparkes/capstone-project/blob/main/CSS%20Architecture%20Package/about.html"
  }
</script>
```
