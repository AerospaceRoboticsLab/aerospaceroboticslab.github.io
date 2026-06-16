# Aerospace Robotics Lab — Website

A self-contained **static** website (plain HTML + CSS, no build step). It deploys
to GitHub Pages by simply serving the files — nothing to compile.

## Files

```
index.html          Home (hero, mission, research thrusts, animations, director)
research.html       Research programs
team.html           PI, students, visiting researchers, alumni
publications.html   Journal / conference / preprint list (filterable)
teaching.html       Courses
blog.html           Posts + "In the news"
contact.html        Address, links, joining the lab
assets/style.css    The single stylesheet (all theming via CSS variables at top)
.nojekyll           Tells GitHub Pages NOT to run Jekyll (serve files as-is)
jekyll-template/    Archived Jekyll version (optional — safe to delete)
```

## Preview locally

Open `index.html` in a browser, or:

```
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Deploy to GitHub Pages (simple, no build)

1. Push these files to the repo's `main` branch. The repo's **root** must contain
   `index.html` and `.nojekyll` (not nested in a subfolder).
2. Settings → Pages → Build and deployment → Source → **Deploy from a branch**.
3. Branch: **main**, folder: **/ (root)** → Save.
4. Live within a minute at your Pages URL
   (for repo `aerospaceroboticslab.github.io`, that's `https://aerospaceroboticslab.github.io/`).

Because `.nojekyll` is present, GitHub serves the HTML directly and will not try
to build it — so the earlier Jekyll/Liquid errors cannot happen.

## Editing

- Colors, spacing, fonts: CSS variables in the `:root { … }` block at the top of
  `assets/style.css`.
- Add a publication: copy a `.pub` block in `publications.html` (set
  `data-t="journal"`, `"conf"`, or `"preprint"`).
- Add a team member: copy a `.person` block in `team.html`.
