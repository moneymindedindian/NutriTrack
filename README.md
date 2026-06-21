# NutriTrack — Daily Supplement Tracker

A single-page web app for tracking daily/weekly supplement intake, food-based nutrient coverage, and progress over time — installable as an app on Android (and addable to the home screen on iOS).

## Short description

> NutriTrack helps you stay consistent with your supplements and nutrition. Set up your profile once, get personalized daily targets (vitamins, minerals, protein, and more), log intake in a tap, and track your streaks — with smart reminders and an installable mobile app experience.

## Features

- **Personalized daily targets** — calculated from your age, sex, weight, activity level, goal, sun exposure, and dietary preference (omnivore/vegetarian/vegan/keto/paleo), based on standard nutrition reference values (RDA/AI).
- **Daily & weekly tracking** — log intake by supplement or by food source, with progress bars and a daily completion ring.
- **Dashboard** — streaks, today's stats, most-deficient nutrients, and quick-log shortcuts.
- **Progress page** — weekly/monthly charts and breakdowns.
- **Customizable tracking list** — presets (Essential, Fitness, Vegan) or pick your own supplements.
- **Health Tips page** — general nutrition and supplement guidance.
- **Reminders**
  - In-app smart reminders (morning/afternoon/evening) when key supplements are running low.
  - Optional browser push notifications (Android Chrome, while the app is open/recently used).
  - **"Add to Phone Calendar"** export (`.ics`) — adds real, recurring daily reminders to your phone's own calendar app, which fire even when NutriTrack is closed. This is the most reliable option on iPhone, where browser notifications aren't supported.
- **Installable PWA** — add it to your Android home screen as a standalone app with its own icon, or use "Add to Home Screen" on iOS.
- **Data import/export** — back up or transfer your data as a JSON file. All data is stored locally in your browser (`localStorage`) — nothing is sent to a server.

## Files included

| File | Purpose |
|---|---|
| `supplement-tracker_v3.html` | The app itself (open this) |
| `manifest.json` | PWA manifest — app name, icons, theme color |
| `sw.js` | Service worker — enables installability + basic offline caching |
| `icon-192.png`, `icon-512.png` | App icons (standard) |
| `icon-192-maskable.png`, `icon-512-maskable.png` | App icons (Android adaptive-icon safe zone) |
| `apple-touch-icon.png` | Icon used for iOS "Add to Home Screen" |

## How to install it as an app

> Service workers and manifests require the app to be served over `http://` or `https://` — opening the HTML file directly from disk (`file://`) will still run the app, but the install/offline features won't activate.

1. Put **all the files above in the same folder** and host them on any static web server (GitHub Pages, Netlify, Vercel, or your own server).
2. On your **Android** phone, open the hosted URL in Chrome.
   - Tap the **"Install App"** button in the nav (appears automatically), or
   - Use Chrome's menu → **"Install app" / "Add to Home screen."**
3. On **iPhone**, open the URL in Safari → Share button → **"Add to Home Screen."** (Note: push notifications aren't supported on iOS for web apps — use the in-app "Add to Phone Calendar" feature instead for reliable reminders.)

## Notes & limitations

- This is a fully client-side app — no backend, no account, no data leaves your device.
- Daily targets are general wellness guidance based on published nutrition references, not medical advice. Always check with a healthcare professional before starting any supplement regimen.
- Browser-based push notifications only work while the browser/app has been recently active; for guaranteed reminders, use the calendar export.
