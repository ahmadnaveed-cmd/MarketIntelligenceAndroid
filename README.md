# Market Intelligence Android — V1.0 starter

This is an Android Studio project (Kotlin + WebView UI) for the first private Android build.

## What is implemented
- Android app shell with internet permission.
- Dashboard covering gold, silver, major indices and major FX pairs.
- Twelve Data quote adapter for live quote requests.
- API key entry and local private storage in Android SharedPreferences.
- Five-pillar score entry: Technical, Sentiment, Macro, Fundamentals, Institutional Positioning.
- Weighted overall score from -10 to +10.
- One-decimal display rounding, using half-up behavior on the absolute magnitude.
- Score snapshots and local history stored on the device.

## Important live-data limitations
- You must supply your own Twelve Data API key. Obtain one from https://twelvedata.com/ and check that your plan supports the symbols and quote frequency you need.
- Symbol availability differs by provider and plan. If an index symbol fails, use the provider's exact supported symbol.
- The app currently retrieves live quotes only. It does **not** yet ingest live CFTC positioning, retail sentiment, central-bank flows, full macro calendars, earnings/fundamentals or institutional order flow. Those pillar values are entered manually in this first implementation and are not fabricated.
- The current weights are transparent prototype defaults (25/15/25/20/15). The next release should implement instrument-specific adaptive weights and validated data connectors before treating automated scores as trading signals.
- This project is source code, not a compiled APK. Build it in Android Studio to generate the installable APK.

## Build an APK
1. Install Android Studio on a PC and open this folder as a project.
2. Allow Android Studio to install the Android Gradle Plugin / SDK components.
3. Build > Build Bundle(s) / APK(s) > Build APK(s).
4. The debug APK will normally be at `app/build/outputs/apk/debug/app-debug.apk`.
5. Transfer the APK to your Android phone, open it, and allow installation from that source if Android asks.

## Suggested next engineering steps
1. Add backend proxy for market-data credentials rather than embedding provider keys in a client app for a public release.
2. Add validated time-series ingestion and calculate technical indicators on 1D and 4H.
3. Add dedicated sources for CFTC COT, retail positioning, economic releases, yields, ETF flows and instrument-specific fundamentals.
4. Add freshness timestamps, source attribution, stale-data detection, missing-data penalties and audit logs.
5. Add automated tests for score weighting, rounding and asset-specific configuration.
