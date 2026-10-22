# EduPulse

Offline classroom clicker quizzes for formative assessment and group quiz bowls. Arduino Nano clickers with HC-05 Bluetooth modules connect straight to the page using Web Serial. Quizzes, classes and results are stored on the device. A thesis project by Jessairra Macinas, BSEd Science, Bicol University Tabaco Campus.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app (HTML, CSS, JS, icons) |
| `sw.js` | Service worker: caches the app, fonts and the Excel library so it works offline. **Must not be empty.** |
| `manifest.webmanifest` | Makes it installable, landscape, standalone |
| `icon-192.png`, `icon-512.png` | App icons |

## Host it

Web Serial needs HTTPS. Upload all five files to the same folder on GitHub Pages, Netlify, static.app or similar.

## Check that offline works

1. Open the hosted page in Chrome on Android with internet.
2. Wait a few seconds. On Home, the chip under Your data should say **Works offline**.
3. Turn on airplane mode and reopen it from the home screen icon. It should load.

If the chip says **Not offline-ready yet**: confirm `sw.js` uploaded with its contents (not 0 bytes) and that the page is served over HTTPS.

## Update the app

Change `index.html`, then bump `CACHE` in `sw.js` (for example `edupulse-v8`) so phones fetch the new version. Open the app online once to pick it up.

## Needs

Chrome on Android 137 or newer, or Chrome/Edge on a computer. Pair each HC-05 in Android Bluetooth settings first. Firmware: `EduPulse_Clicker_v3.ino` (the button pins at the top must match your wiring).

## Your data

Everything lives in the browser on that device. Use Back up on Home regularly; Restore loads a backup on another device.
