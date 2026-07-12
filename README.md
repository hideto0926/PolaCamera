# POLACAM — landing page

Bilingual (日本語 / EN) landing page for **POLACAM**, a Polaroid-style camera app
whose finished prints look blank white and "develop" (rise up) on long-press via
Live Photo.

Live (after deploy): https://hideto0926.github.io/POLACAM/

## Files
- `index.html` — the landing page (inline CSS/JS, no build step)
- `privacy.html` — privacy policy (JA + EN summary)
- `assets/` — icon, OG image and app screenshots
- `.nojekyll` — serve files as-is on GitHub Pages

## Assets
- `icon.png`, `og.png` — from `POLACAM/icon/ICON.png`
- `shot-*.jpg` — app screenshots converted from `POLACAM/sozai/*.HEIC`
  (menu / shoot / develop-eject / handwriting / settings / gallery-reveal)

## Deploy (GitHub Pages)
1. Push the contents of this folder to the root of the `POLACAM` repo, default branch.
2. Repo → Settings → Pages → Source: *Deploy from a branch* → branch = default, folder = `/ (root)`.
3. Open https://hideto0926.github.io/POLACAM/.

## Notes
- Language defaults to the browser language and can be toggled top-right; the choice
  is stored in `localStorage` (`pola_lang`).
- The App Store CTA is a "Coming soon" placeholder — replace the `.soon` block with an
  `<a class="soon" href="...">` once the app is live.
- Also registered as a card in the apps index (`homepageRoot/index.html`,
  icon `assets/polacam.png`).
- Contact email: hideto0926@gmail.com
