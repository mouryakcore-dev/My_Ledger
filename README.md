# My Ledger

A personal budget tracker — income, expenses, debts, bills, savings, and IOUs — synced live across devices via Firebase Firestore, installable as a home-screen app via GitHub Pages.

## Files
- `app.html` — the entire app (HTML/CSS/JS in one file). This is the file GitHub Pages serves.
- `manifest.json` — PWA metadata (name, icons, theme color) so it installs like a real app.
- `sw.js` — service worker, lets the app load offline once visited.
- `icon-192.png` / `icon-512.png` — app icons.

## Live URL
https://mouryakcore-dev.github.io/My_Ledger/app.html

## Making changes
1. Edit `app.html` (or other files) locally in VS Code.
2. Commit and push to `main`.
3. GitHub Pages rebuilds automatically within a minute or two.
4. If `app.html` changed, bump the `CACHE` version string in `sw.js` (e.g. `ledger-cache-v2` → `v3`) so phones/browsers pick up the new version instead of serving a stale cached copy.
5. Refresh the app on each device (may need a hard refresh / reopen once) to see the update.

## Firebase
Sync is powered by a Firestore database (project `my-ledger-89067`). The config keys in `app.html` are not secret — access to your data is controlled by your personal passcode (set on first load of the app) plus Firestore rules.

**Important:** the Firestore security rules were created in test mode and expire **29 July 2026**. Before then, go to Firebase Console → Firestore Database → Rules, and update them to not have an expiry (e.g. restrict by a simple rule rather than a date cutoff), or the app will stop syncing.
