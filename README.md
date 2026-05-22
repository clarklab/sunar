# sunar

Mobile-first installable camera overlay for finding today's sunrise and sunset bearings with GPS, compass, gyro, wake lock, and haptic alignment.

## Run locally

```sh
python3 -m http.server 5173
```

Then open `http://localhost:5173`. Camera, motion permissions, service workers, and Add to Home Screen behavior require HTTPS or localhost in most mobile browsers.

## Deploy to Netlify

This is a static app. Netlify should use:

- Build command: none
- Publish directory: `.`
- Config file: `netlify.toml`

For Git-based deploys, connect the repo in Netlify and keep the default static-site settings above. For the Netlify CLI:

```sh
netlify deploy --dir .
netlify deploy --prod --dir .
```

Netlify's HTTPS hosting is required for camera, GPS, compass/gyro permissions, service worker registration, and Add to Home Screen install behavior on mobile.

## App icons

The browser favicon uses lightly rounded PNG/ICO assets derived from `sunar-icon.webp`. The install manifest keeps standard square icons and separate `maskable` icons, so Android and Chromium-based browsers can apply their own adaptive icon masks. The Apple touch icon stays opaque and square because iOS applies its own home-screen rounding.
