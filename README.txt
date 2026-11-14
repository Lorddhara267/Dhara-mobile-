NKANE — DHARA CRT GOLD ENGINE (MOBILE PWA)
Version: 1.2 · Mobile-first · XAUUSD-first

WHAT IS INCLUDED
- Responsive dark glass / antique-gold mobile interface
- Command Centre with XAUS indicative XAU/USD spot feed and recorded intraday reference series
- Manual CRT/ICT analysis checklist and bias/timeframe controls
- Cash risk budget, stop distance and R:R calculator
- Trade journal stored in this browser's local storage
- CSV journal export
- PWA manifest, 192px/512px app icons, install prompt and offline service worker

RUN / TEST LOCALLY
1. From this folder run: python3 -m http.server 8000
2. Open http://localhost:8000 in a browser.
3. Test navigation, calculator, saving an analysis, saving a trade and CSV export.
4. Service worker and installability require localhost or an HTTPS deployment.

INSTALL ON ANDROID TODAY (PWA)
1. Publish this folder to an HTTPS static host (all files and folders must retain their paths).
2. Open the HTTPS address in Chrome on Android.
3. Use the in-app INSTALL prompt if Chrome offers it, or Chrome menu > Install app / Add to Home screen.
This creates a home-screen app experience; it is not an APK file.

GENERATE A REAL ANDROID APK
PWABuilder / Bubblewrap can package this PWA as a Trusted Web Activity, but first it must be deployed to HTTPS with a valid manifest. See:
https://github.com/pwa-builder/PWABuilder/blob/main/docs/builder/android.md
Then enter the deployed URL at https://www.pwabuilder.com/ and choose Android packaging. A generated APK must be installed and tested on the target phone. For a clean full-screen TWA, deploy the generated Digital Asset Links file at /.well-known/assetlinks.json.

IMPORTANT PRODUCT LIMITATIONS
- XAUS integration: /api/v1/spot?compact=1 for indicative spot; refreshes at 60-second intervals. /api/v1/intraday?symbol=xau&hours=24 provides recorded spot samples (approximately every 5 minutes).
- The recorded intraday series is a spot-price line, not OHLC candles. It does not supply broker-specific 5m/15m candle history for CRT analysis.
- XAUS spot is an indicative mid-market reference, not a tradable broker quote. The app checks source timestamps and labels stale/unverified states; it never invents a fallback price.
- The scanner records manual observations; it does not independently detect liquidity sweeps, displacement or FVGs.
- No automated trading signals or broker execution are implemented.
- MT5 integration requires a separately hosted, authenticated bridge. Never place broker credentials in this frontend.
- Lot size is intentionally not calculated until the broker's contract size, tick size/value and account currency are known.
- Journal data is stored only in this browser on this device. Export CSV backups regularly; clearing browser data can remove it.

This is an installable-PWA-ready frontend prototype, not a production trading system. Verify all market data and broker specifications before using it for trading decisions.

DATA SOURCE
- XAUS Gold Data API documentation: https://xaus.com/api/
- Spot endpoint is cached at approximately 60 seconds; observe the returned data_state, price_as_of and updated_at fields.
- Intraday series is a recorded reference series, not a broker execution feed.
