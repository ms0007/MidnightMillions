# MidnightMillions — Landing Page Demo

This repository contains a self-contained HTML landing page for the *Midnight Millions* ebook concept. It has no server-side application, payment integration, user database, or build toolchain.

## Preview locally

Open `ebook_midnight_millions.html` directly in a modern browser, or serve the directory with a local static HTTP server:

```sh
python -m http.server 8080
```

Then visit `http://localhost:8080/ebook_midnight_millions.html`.

## Production-readiness findings

- **Checkout is not wired.** The primary “Get Midnight Millions” link currently points to `#`; it scrolls to the page top and does not initiate a purchase. Replace it with the actual Gumroad or other payment-provider product URL and verify the end-to-end checkout before launch.
- **Verify scarcity and price claims.** The page says “First 100 copies only” and mentions a later ₹999 price. Keep those statements only if they match the actual offer and are enforced operationally.
- **External dependency.** Fonts are loaded from Google Fonts. A deployment that requires self-contained/offline rendering should self-host the fonts and test the typography.
- **Accessibility pass still needed.** Validate keyboard access and screen-reader behavior for the clickable chapter cards, focus states, color contrast, and reduced-motion preferences.
- **No automated test/build suite exists.** This is a static demo. Before launch, add a smoke test for link targets and run responsive/accessibility checks against the actual deployment URL.

## Current scope

The page is intended as a concept/demo, not a live digital-products checkout. No payment endpoint or user data store should be inferred from the landing-page appearance.
