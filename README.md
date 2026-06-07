# Noor Prayer Times

Noor is a lightweight prayer-times web app focused on one thing: giving fast, trustworthy prayer information for the user’s current location.

It combines prayer calculations, qibla direction, location lookup, and a clean countdown-focused interface in a simple static project that can be served anywhere.

## Highlights

- Location-aware daily prayer times
- Current prayer and next prayer countdown
- Qibla direction and nightly Sunnah timing helpers
- Search, map selection, GPS, and IP-based location detection
- Light and dark theme support
- PWA support with manifest, service worker, and install metadata
- Social link preview metadata for sharing

## Project Structure

- `noor.html` — main application UI, styles, and logic
- `manifest.webmanifest` — PWA manifest
- `sw.js` — service worker for caching the app shell
- `favicon.svg` — favicon
- `icon.svg` — app/share icon
- `PRODUCT.md` — product and design context

## Tech Stack

- Plain HTML, CSS, and JavaScript
- `adhan` for prayer time calculations
- `Leaflet` for map interaction
- OpenStreetMap / Nominatim for search and reverse geocoding

## How It Works

Noor calculates prayer times from the selected location and chosen calculation settings. The hero section emphasizes:

- the prayer currently in progress
- how long it has been active
- the next prayer
- the remaining time until it starts

Users can set location in several ways:

- GPS location
- map click or drag
- text search
- fallback IP detection

## Running Locally

You can open `noor.html` directly, but some browser features are limited on `file://` URLs.

Recommended: serve the folder over a local HTTP server.

Example options:

```bash
python -m http.server 8000
```

or

```bash
npx serve .
```

Then open:

```text
http://localhost:8000/index.html
```

If your deployed entry file is named `index.html`, keep the manifest and service worker paths aligned with that deployment file.

## PWA Notes

Noor includes:

- a web manifest
- a service worker
- install-friendly metadata
- favicon and app icon assets

Important:

- Full PWA install behavior will not work from `file://`
- Service workers require `https` or `http://localhost`
- For deployment, ensure your main served page matches the manifest `start_url`

## Social Preview Notes

The app includes Open Graph and Twitter meta tags for link previews.

For best production previews:

- replace relative URLs with your real deployed absolute URL
- use an absolute image URL for preview images
- validate previews with platform-specific debuggers if needed

## Deployment Checklist

1. Serve the app over `https` or `http://localhost` during testing.
2. Make sure the main entry file name matches the manifest and service worker cache list.
3. Update Open Graph and Twitter URLs to your deployed domain.
4. Confirm the service worker is registering successfully in production.
5. Test installability in Chrome or Edge.

## Product Direction

Noor is designed to feel:

- calm
- precise
- modern

The UI should prioritize fast reading and trust over decoration.

## Future Improvements

- dedicated offline fallback page
- richer install prompt UX
- share image asset tailored for social previews
- localization and multilingual prayer naming
- persistent saved user settings export/import
