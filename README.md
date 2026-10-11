# Repwise — customizable training MVP

A lightweight, installable web app (PWA) for iPhone, with local-only workout data.

## What's included
- Full-body A/B/C starter plan: push, legs, glutes, back, shoulders and core
- Edit workout names, training days, rest, exercises, sets, reps and cues
- Add/remove exercises and add new workout plans
- Workout logging by set, session notes and a rest timer
- History, simple best-session records, weekly session count and total reps
- JSON export/import backup and reset
- Offline shell after first successful load (via service worker)

## Important MVP limitations
- Data is stored in this browser's localStorage. It is not encrypted, synced, or automatically backed up.
- Progression is guided by a written rule rather than an automated recommendation engine.
- The “best session” metric is total logged reps for an exercise, not a scientifically normalized strength score.
- Timer notifications/vibration can be limited by iOS when the app is backgrounded. Keep the app open during rest periods.
- This is a training tracker, not medical advice. Stop if you feel sharp pain; choose exercises you can do safely.

## Run locally on Windows
You can open `index.html` directly to test most features. For PWA installation and offline caching, serve it over HTTPS (or localhost).

### Quick local test
1. Install Python 3 if needed.
2. Open PowerShell in this folder.
3. Run: `py -m http.server 8000`
4. On the same computer, open `http://localhost:8000`.

## Install on iPhone (recommended)
A PWA must be hosted over HTTPS for reliable Add to Home Screen and service worker support.
1. Create a free GitHub account if you don't have one.
2. Create a new repository, e.g. `repwise`.
3. Upload `index.html`, `manifest.json`, `service-worker.js`, `icon-192.png`, and `icon-512.png` to the repository root.
4. In the repository, open Settings → Pages, enable deployment from the main branch/root, and wait for the HTTPS Pages URL.
5. On your iPhone, open that URL in Safari → Share → Add to Home Screen.
6. Launch Repwise from the Home Screen. Create a small test workout, close/reopen it, and confirm the log persists.
7. In Progress, use Export data periodically to keep a backup.

## Updating
Upload the updated files to the same hosting location. If the service worker serves an old version, close the app and reopen it; if needed, remove the Home Screen app and add it again.

## Privacy
The app has no analytics, account, server-side database, or external API. Workout data is saved in localStorage on the device/browser profile. Hosting only serves the static app files; your workout logs are not sent to the host.
