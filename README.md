# personal-web

Personal academic homepage for Junyu Zhang (Astronomy, University of Arizona).

Static HTML/CSS — no build step, no dependencies, nothing to install.

```
index.html         About, education, talks, honors, contact
research.html      Research narrative
publications.html  Refereed publication list
style.css          Shared styles (light + dark mode)
assets/            Images
```

## Preview locally

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

Any port works. On a remote devserver, bind all interfaces and use the host name:

```bash
python3 -m http.server 44101 --bind ::
# open http://<devserver>:44101/index.html
```

## Deploy

Hosted on GitHub Pages. One-time setup, done by the repo owner in the browser:

1. Make the repo public: **Settings** → **General** → scroll to **Danger Zone** →
   **Change visibility** → Public. Pages requires this on a free account.
2. **Settings** → **Pages** (left sidebar, under "Code and automation").
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`.
4. Set **Branch** to `main` and the folder to `/ (root)`, then **Save**.
5. Wait 1–2 minutes and refresh — the page will show `Your site is live at …`.

The site lands at `https://<owner>.github.io/personal-web/`, or at
`https://<owner>.github.io/` if the repo is renamed to `<owner>.github.io`.

A custom domain can be attached later on the same **Pages** settings screen.

### Publishing changes

After the one-time setup there is no deploy command — pushing is the deploy:

```bash
git add -A
git commit -m "Update publications"
git push
```

GitHub rebuilds automatically and the live site updates within a minute or two.

All internal links are relative, so the site works from either a subpath or the domain root.

## TODO

- Point the ADS link in `index.html` at a real author library (currently the generic
  `ui.adsabs.harvard.edu/public-libraries/` landing page).
- Update the citation count in `publications.html` when it changes.
- Downscale `assets/IMG_6830.jpg` (currently 5.6 MB, 3633×5394) to roughly 800 px wide —
  it is displayed at 190 px and git keeps every version forever.
