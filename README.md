# EndoDepth-X 2027 — challenge website

Static site for the proposed IEEE ISBI 2027 challenge. Plain HTML + CSS, no build step,
no JavaScript. Everything lives in `index.html`; images in `assets/`.

## Deploy to GitHub Pages

1. Create a repo — the org account is best, e.g. `endodepth-x/endodepth-x.github.io`,
   or a personal repo named `endodepth-x`.
2. Push the contents of this folder to the default branch.
3. Settings → Pages → Source: *Deploy from a branch* → `main` / `root`.
4. Live in about a minute at `https://<user-or-org>.github.io/<repo>/`.

```bash
git init
git add .
git commit -m "Add EndoDepth-X 2027 challenge site"
git branch -M main
git remote add origin git@github.com:<user>/<repo>.git
git push -u origin main
```

`.nojekyll` is present so GitHub serves the files as-is instead of running Jekyll.

## Preview locally

```bash
python -m http.server 8931
# http://127.0.0.1:8931/
```

## Assets

Figures are crops from Reyes-Amezcua et al., *EndoDepth* (arXiv:2409.19930), regenerable
from the paper PDF:

- `k_*.jpg` — 16 corruption examples, cropped above the figure's burned-in labels so the
  site can set its own typography.
- `c_<model>_<corruption>.jpg` — the input / ground-truth / prediction grid.
  Models: `rgb`, `gt`, `mono2`, `afsfm`, `monovit`, `endosfm`.
  Corruptions: `ld` (lens distortion), `rc` (resolution change), `sr` (specular
  reflection), `cc` (colour change). Only the `sr` row is used on the page today; the rest
  are cropped and ready for future sections.
