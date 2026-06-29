# My Ledger

My Ledger is a personal finance tracker for managing income, expenses, debts, bills, savings, and IOUs. It syncs data across devices through Firebase Firestore and can be installed as a progressive web app.

## Project files
- app.html — the full app UI, styles, and logic in a single file.
- manifest.json — PWA metadata for installation and app appearance.
- sw.js — service worker for offline support and caching.
- icon-192.png and icon-512.png — app icons.

## Live app
https://mouryakcore-dev.github.io/My_Ledger/app.html

## Updating the app
1. Edit the files locally in VS Code.
2. Commit your changes.
3. Push to the main branch.
4. If app.html changes, update the cache version in sw.js so installed browsers fetch the new version.
5. Refresh the app on your device if the old version still appears.

## Firebase sync
The app uses Firebase Firestore for syncing. The config values in app.html are not secrets, and access is protected by your personal passcode plus Firestore security rules.

> Important: the current Firestore rules are in test mode and expire on 29 July 2026. Before that date, update them in the Firebase console to a safer permanent rule, or syncing will stop.
