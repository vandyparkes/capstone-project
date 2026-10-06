# Structured Data and Social Preview Check

Page: About (`CSS Architecture Package/about.html`).

## 1. Open Graph

`og:title` matches `<title>About | Bulletproof Personal Training</title>`.

`og:description` matches `meta name="description"`. The page shows the trainer background, the credentials list, and the platform list.

`og:url` is the About file on `main`. That URL returned `200` and `text/html`.

`og:type` is `website`.

`og:image` is the Training spaces photo captioned `Home gym coaching` (`images/home-gym-800.jpg`). Visible alt: `Trainer in a grey shirt squatting with a loaded barbell in a garage.` That URL returned `200` and `image/jpeg`.

```html
<meta property="og:title" content="About | Bulletproof Personal Training">
<meta property="og:description" content="Trainer background, credentials, and platform list for Bulletproof Personal Training.">
<meta property="og:url" content="https://github.com/vandyparkes/capstone-project/blob/main/CSS%20Architecture%20Package/about.html">
<meta property="og:type" content="website">
<meta property="og:image" content="https://raw.githubusercontent.com/vandyparkes/capstone-project/main/CSS%20Architecture%20Package/images/home-gym-800.jpg">
<meta property="og:image:alt" content="Trainer in a grey shirt squatting with a loaded barbell in a garage.">
<meta property="og:image:width" content="800">
<meta property="og:image:height" content="533">
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
    "description": "Trainer background, credentials, and platform list for Bulletproof Personal Training.",
    "url": "https://github.com/vandyparkes/capstone-project/blob/main/CSS%20Architecture%20Package/about.html"
  }
</script>
```

## 4. Validation

Tool: [W3C Nu Html Checker](https://validator.w3.org/nu/?showoutline=yes#textarea). Document upload.

First check, one error. Line 58. `p` was not allowed inside `figure` after `figcaption`.

`figcaption` is the last child of `figure`. The caption and the `Watch tutorials` link are inside it.

Second check, no messages.

Schema Markup Validator, `about.html`. One `AboutPage` node. 0 errors. 0 warnings.

## 5. What the metadata supports

The Open Graph tags supply a preview title, description, page URL, type `website`, and the Home gym coaching image.

The JSON-LD states the page is an `AboutPage`. `name` is `About the trainer`. `description` and `url` match the tags above.

A platform can skip that title, description, or image. The metadata does not set a search rank. The credentials list stays text on the page.

Claim: these tags do not guarantee that About ranks for personal training.

## Reflection

I would not claim that these tags make About rank for personal training. They do not guarantee a search rank.


