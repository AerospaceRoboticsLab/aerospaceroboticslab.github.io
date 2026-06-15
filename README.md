# Aerospace Robotics Lab — Website

A self-contained static website for the Aerospace Robotics Lab at Georgia Tech.
Pure HTML + CSS with a custom **"Mission Control"** visual identity (deep-space
canvas, telemetry palette, orbital motifs). **No build step required** — it
deploys directly to GitHub Pages.

## Files

```
index.html          Home (hero, mission, research thrusts, PI)
research.html       Research programs & projects
team.html           PI, PhD, MS, undergrad, visiting members
publications.html   Journal + conference papers (filterable)
contact.html        Contact & prospective-student info
assets/style.css    Single shared stylesheet (the design system)
```

## Preview locally

Just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to GitHub Pages

1. Create a new repository on GitHub (e.g. `aerospace-robotics-lab`).
2. Push these files to the `main` branch:
   ```bash
   git init
   git add .
   git commit -m "Initial lab website"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Select branch **main**, folder **/ (root)**, and **Save**.
6. Your site goes live at `https://<you>.github.io/<repo>/` within a minute or two.

> For a custom domain (e.g. the gatech address), add it under
> Settings → Pages → Custom domain.

## Editing

- **Colors / fonts / spacing:** all CSS variables live at the top of
  `assets/style.css` (`:root { … }`). Change `--cyan`, `--gold`, `--void`, etc.
  in one place to re-theme the whole site.
- **Add a team member:** copy a `.person` block in `team.html`.
- **Add a publication:** copy a `.pub` block in `publications.html` and set
  `data-t="journal"` or `data-t="conf"` so the filter tabs work.

## Photos

Member and PI photos are currently linked from the existing lab site
(`aerospaceroboticslab.ae.gatech.edu`). For a fully self-contained repo,
download the images into an `assets/img/` folder and update the `src` paths.
