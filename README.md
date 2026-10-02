# ML for Physicists

Source for **ML for Physicists by Ethan**, a [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
site publishing lecture notes, exercises, and worked Jupyter notebooks, deployed to GitHub Pages.

## Preview locally

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
mkdocs serve
```

Then open http://127.0.0.1:8000.

## Project layout

```
mkdocs.yml                  # site config, nav, theme
docs/
  index.md                  # home page
  about.md
  materials/                # lectures / exercises / resources
  notebooks/                # rendered .ipynb notebooks
  stylesheets/extra.css     # minimal styling tweaks
  javascripts/mathjax.js    # math rendering config
.github/workflows/ci.yml    # builds + deploys to GitHub Pages on push to main
```

## Adding content

- **A new page**: add a `.md` file under `docs/`, then add it to `nav:` in `mkdocs.yml`.
- **A new notebook**: run it and save it with the outputs you want shown, drop the `.ipynb` into
  `docs/notebooks/`, then add it to `nav:` (notebooks are rendered via `mkdocs-jupyter` and are
  **not** re-executed at build time — see `docs/notebooks/index.md`).

## First-time setup on GitHub

1. Create a new **public** repository, e.g. `ml-for-physicists`, under your GitHub account.
2. Push this folder to it:
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/ml-for-physicists.git
   git push -u origin main
   ```
3. In the repo's **Settings → Pages**, set the source branch to `gh-pages` (this branch is created
   automatically the first time the GitHub Action in `.github/workflows/ci.yml` runs).
4. Update the placeholders in `mkdocs.yml` (`site_url`, `repo_url`) and in `docs/about.md` with
   your actual GitHub username / contact details, then commit and push again.
5. Your site will be live at `https://<your-username>.github.io/ml-for-physicists/` a minute or
   two after the Action finishes (check the **Actions** tab for build status).

## Why Material for MkDocs (and not Zensical)

[Zensical](https://github.com/zensical/zensical) is a new static site generator from the same team
behind Material for MkDocs, but it's still pre-1.0: its plugin/module system — which is what
`mkdocs-jupyter` would need to hook into to render notebooks — hasn't shipped yet. Material for
MkDocs is the mature, stable option today, with a large plugin ecosystem (including
`mkdocs-jupyter`) and first-class GitHub Pages support, so that's what this site uses.

Two things worth knowing for later:

- **`mkdocs<2` is pinned in `requirements.txt` on purpose.** A separate, unrelated maintainer is
  building a ground-up "MkDocs 2.0" rewrite that drops the plugin system entirely (which would
  break both `mkdocs-jupyter` and Material for MkDocs itself). It has no release date and isn't a
  near-term risk — current 9.x/1.x versions keep working — but the pin stops an automatic upgrade
  into it.
- **Zensical is the Material team's own answer to that**, explicitly positioned as a future
  "drop-in replacement for MkDocs 1.x." It's worth revisiting once its module system (and, ideally,
  a notebook-rendering module) ships — at that point migrating should be low-effort, since Zensical
  is designed to read existing Material for MkDocs config with minimal changes.
