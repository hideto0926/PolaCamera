# POLACAM — landing page

Bilingual (日本語 / EN) landing page for **POLACAM**, a Polaroid-style camera app
whose finished prints look blank white and "develop" (rise up) on long-press via
Live Photo.

Live (after deploy): https://hideto0926.github.io/PolaCamera/

## Files
- `index.html` — the landing page (inline CSS/JS, no build step)
- `privacy.html` — privacy policy (JA + EN summary)
- `assets/` — icon, OG image and app screenshots
- `.nojekyll` — serve files as-is on GitHub Pages

## Assets
- `icon.png`, `og.png` — from `POLACAM/icon/ICON.png`
- `ss/{ja,en}-01..06.jpg` — App Store screenshots (web size), made from
  `POLACAM/AppStore/screenshots/{ja,en}/*.png` (see `POLACAM/AppStore/src/gen.py`)
- `demo.jpg` — sample photo used by the 3D hero print and the "How it works" illustrations
- `demo-photo.js` — `demo.jpg` embedded as a data URL. The 3D prints load the photo from here so it
  also works when `index.html` is opened directly from disk (`file://`), where a normal image would make
  the WebGL texture black. Regenerate it if you replace `demo.jpg`.
- `shot-*.jpg` — older app screenshots (no longer referenced by `index.html`)

## three.js hero
- `three.js r128` from cdnjs. A fixed full-page canvas shows Polaroid prints drifting in depth;
  the camera descends as you scroll.
- The main print follows `#print-anchor` in the hero. Pressing and holding develops it with a
  custom shader (white → mottled teal → full color); releasing turns it white again.
  After 6 s without input it develops by itself as a demo.
- `?reveal=0.6` pins the develop progress (for screenshots / checks).
- Falls back to a static photo (`.nogl`) when WebGL is unavailable.

## Deploy (GitHub Pages)
1. Push the contents of this folder to the root of the `POLACAM` repo, default branch.
2. Repo → Settings → Pages → Source: *Deploy from a branch* → branch = default, folder = `/ (root)`.
3. Open https://hideto0926.github.io/PolaCamera/.

## Notes
- Language defaults to the browser language and can be toggled top-right; the choice
  is stored in `localStorage` (`pola_lang`).
- The App Store CTA is a "Coming soon" placeholder — replace the `.soon` block with an
  `<a class="soon" href="...">` once the app is live.
- Also registered as a card in the apps index (`homepageRoot/index.html`,
  icon `assets/polacam.png`).
- Contact email: hideto0926@gmail.com
