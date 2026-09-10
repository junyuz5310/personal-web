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

## Deploy to GitHub Pages

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin git@github.com:<username>/personal-web.git
git push -u origin main
```

Then enable Pages, in the repo's own settings (not on the GitHub Pages site):

1. Go to `github.com/<username>/personal-web/settings/pages` — or: repo home → the
   **Settings** tab at the far right of the top tab row → **Pages** in the left sidebar,
   under "Code and automation".
2. Under **Build and deployment**, set **Source** to `Deploy from a branch`.
3. Set **Branch** to `main` and the folder to `/ (root)`, then **Save**.
4. Wait 1–2 minutes and refresh — the same page will show `Your site is live at …`.

Do this *after* the push: the branch dropdown is empty until the repo has commits.
The **Settings** tab is only visible to the repo owner, and Pages on a free account
requires a public repo (private repos need GitHub Pro).

There is no server to start — GitHub serves the files directly. The site lands at
`https://<username>.github.io/personal-web/`, or at `https://<username>.github.io/`
if the repo is named `<username>.github.io`.

All internal links are relative, so the site works from either a subpath or the domain root.

## TODO

- Point the ADS link in `index.html` at a real author library (currently the generic
  `ui.adsabs.harvard.edu/public-libraries/` landing page).
- Update the citation count in `publications.html` when it changes.
- Downscale `assets/IMG_6830.jpg` (currently 5.6 MB, 3633×5394) to roughly 800 px wide —
  it is displayed at 190 px and git keeps every version forever.
