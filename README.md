# 3D Rubik's Cube Trainer (PWA)

An installable web app: a 3D cube you can drag, with all 57 OLL cases and 21 PLL cases,
step-by-step animation, and a paint mode. Works offline after the first visit.

## Put it on GitHub Pages

1. On github.com, click **New repository**. Name it (for example `cube-trainer`), keep it **Public**, and create it.
2. Click **uploading an existing file**, then drag in **everything inside this folder**
   (`index.html`, `sw.js`, `manifest.webmanifest`, `three.min.js`, `THREE-LICENSE.txt`, `.nojekyll`, and the `icons` folder).
   Upload the files themselves, not the folder that contains them. Then click **Commit changes**.
   (If `.nojekyll` is hidden on your computer, skip it. The app still works.)
3. Open **Settings > Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**,
   choose **main** and **/ (root)**, then click **Save**.
4. Wait about a minute. Your app will be at `https://YOUR-USERNAME.github.io/cube-trainer/`.
   GitHub shows the link at the top of the Pages screen.

## Install it on your devices

Open your GitHub Pages link, then:

- **iPhone or iPad (Safari):** Share button, then **Add to Home Screen**.
- **Android (Chrome):** menu, then **Install app** (or use the **Install app** button on the page).
- **Windows or Mac (Chrome or Edge):** click the install icon in the address bar, or use the **Install app** button on the page.
- **Mac (Safari):** File, then **Add to Dock**.

After the first visit it opens offline.

## Updating the app

1. Edit or replace the file on GitHub.
2. In `sw.js`, change `const CACHE_VERSION = 'v1';` to `'v2'` (then `'v3'`, and so on).
   Without this, devices keep showing the old cached copy.
3. Close and reopen the app once or twice to load the update.

## Files

- `index.html`: the whole trainer
- `three.min.js`: 3D library (three.js r128, MIT license), stored locally so it works offline
- `manifest.webmanifest`: app name, colors and icons
- `sw.js`: service worker that makes it work offline
- `icons/`: app icons (regular, maskable, Apple touch, favicon)

## Notes

- The service worker only runs over `https://` (GitHub Pages does this) or `localhost`.
  Opening `index.html` straight from your disk shows the trainer but does not install or work offline.
- To test on your computer first: run `python3 -m http.server 8000` in this folder,
  then open `http://localhost:8000`.
