# A. D'Mae Diamonds - Website Code Repository

Squarespace code injections and custom page code for [admaediamonds.com](https://www.admaediamonds.com).

## Structure

```
site-global/           # Site-wide Squarespace code injections
  custom-css.css       # Settings > Advanced > Custom CSS
  footer-injection.html # Settings > Advanced > Code Injection > Footer

pages/
  blog/                # Blog post page code injections
  services/            # Service & landing page code injections
  other/               # Other page code injections (portfolio, etc.)
```

## How Code Injection Works in Squarespace

Each file in this repo corresponds to a code injection location in Squarespace:

- **Site-global** files are injected across all pages via Settings > Advanced
- **Page-level** files are injected per-page via Page Settings > Advanced > Page Header Code Injection

## Deployment

This repo is the **source of truth** for all custom code. To deploy changes:

1. Edit the file in this repo and commit
2. Copy the updated code into the corresponding Squarespace code injection field
3. Preview the page in Squarespace before publishing

## File Naming Convention

Page files are named to match their Squarespace URL slug:
- `custom-engagement-rings-los-angeles.html` = admaediamonds.com/custom-engagement-rings-los-angeles
- `blog/lab-grown-vs-natural-diamonds.html` = admaediamonds.com/blog/lab-grown-vs-natural-diamonds
