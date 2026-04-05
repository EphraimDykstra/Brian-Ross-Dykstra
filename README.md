# Brian Ross Dykstra — Memorial Star Tracker

A web application to locate and track the star named in memory of **Brian Ross Dykstra**, located in the constellation Columba.

Point your iPhone at the sky, follow the on-screen reticle, and lock onto his star in real time.

---

## The Star

| Field | Value |
|---|---|
| Name | Brian Ross Dykstra |
| Right Ascension | 06h 03m 18.55s |
| Declination | −29° 39′ 39.6″ |
| Constellation | Columba |

---

## How to Use

1. Open **brianrossdykstra.com** in **Safari** on your iPhone
2. Tap **Find His Star**
3. Allow Location access when prompted
4. Allow Motion & Orientation access when prompted
5. Hold your phone upright, camera toward the sky
6. Follow the arrows — turn and tilt your phone until the reticle locks gold
7. Optionally tap **Camera On** to see the live sky behind the reticle

---

## Technical Notes

- Pure HTML/CSS/JavaScript — no frameworks, no build step, no backend
- All astronomy math runs locally (sidereal time, hour angle, altitude/azimuth conversion)
- Uses `DeviceOrientationEvent` with `webkitCompassHeading` for accurate compass on iOS
- Uses the browser Geolocation API for your position
- Works as a Progressive Web App — tap **Add to Home Screen** in Safari to install it like a native app
- Accuracy is typically within 1–3 degrees depending on device calibration

### Browser Compatibility

| Browser | Works |
|---|---|
| Safari on iPhone | Yes — full support |
| Chrome on Android | Yes |
| Chrome on iOS | No — Apple restricts sensor access to Safari only |
| Desktop browsers | Partial — star position displays but no orientation sensors |

---

## Publishing (GitHub Pages)

This repository is designed to be hosted on **GitHub Pages** pointing to `brianrossdykstra.com`.

Steps:
1. Push this repository to GitHub
2. Go to Settings → Pages → Source: `main` branch, `/ (root)`
3. Purchase `brianrossdykstra.com` and add a CNAME record pointing to `your-username.github.io`
4. Add a `CNAME` file to the repo root containing `brianrossdykstra.com`

---

## Future Plans

- [ ] Tribute and biography section for Brian Ross Dykstra
- [ ] Photo gallery
- [ ] Guestbook / message wall for family and friends

---

*Built with care in memory of Brian Ross Dykstra.*
