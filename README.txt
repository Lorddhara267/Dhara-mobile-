NKANE — DHARA CRT GOLD ENGINE (MOBILE PWA SOURCE)

Files:
- index.html: responsive mobile-first app
- manifest.webmanifest: install metadata
- sw.js: basic offline cache (requires HTTPS hosting)

Run locally:
Open index.html in a modern browser. The app works as a browser prototype; install/offline PWA features require serving over HTTPS (or localhost).

Android install:
1. Host the three files together on an HTTPS static host.
2. Open the hosted URL in Chrome on Android.
3. Use Chrome menu > Install app / Add to Home screen.

Important limitations:
- No live market data is connected. The chart is illustrative and explicitly labelled NOT LIVE.
- No automated signal generation or broker execution is implemented.
- No MT5 credentials should be stored in this frontend. A secure backend/bridge is required.
- Risk calculator computes cash risk budget, stop distance and optional R:R. It intentionally does not calculate lot size until broker contract specifications are known.
- Journal uses browser localStorage. Export CSV backups before clearing browser data or changing devices.

This is a functional frontend prototype, not a production trading system or APK.
