# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A memorial Progressive Web App (PWA) for Brian Ross Dykstra that lets users point their iPhone at the sky to find and lock onto his named star in the constellation Columba.

**Star coordinates:** RA 06h 03m 18.55s, Dec −29° 39′ 39.6″

## Architecture

Everything lives in a single `index.html` file — no build step, no framework, no backend. All CSS, HTML, and JavaScript are inline.

**JS logic inside `index.html`:**
- Starfield canvas animation (animated background stars)
- Astronomy math: sidereal time → hour angle → altitude/azimuth conversion (all client-side)
- Device orientation: `DeviceOrientationEvent` with `webkitCompassHeading` for iOS compass heading
- Geolocation API for user position
- Camera overlay via `getUserMedia`
- Reticle lock detection: compares device az/alt against computed star az/alt with a threshold

**Screens:** Two states managed by toggling the `.gone` CSS class — `#s-intro` (landing) and `#s-track` (active tracker).

**PWA:** `manifest.json` + `apple-mobile-web-app-capable` meta tags. Requires `icon-192.png` and `icon-512.png` (not in repo).

## Deployment

Hosted on GitHub Pages at `brianrossdykstra.com`. The `CNAME` file contains the custom domain. No CI/CD — push to `main` deploys automatically.

## Browser Compatibility

- **Safari on iPhone** — full support (sensors work)
- **Chrome on Android** — works
- **Chrome on iOS** — no sensor access (Apple restriction)
- **Desktop** — star position displays but no orientation

## Development

Open `index.html` directly in a browser or use any static file server (e.g. `python3 -m http.server`). Sensor features require Safari on a real iOS device — desktop testing is limited to the intro screen and star position math.
