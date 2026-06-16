# Aerospace Robotics Lab — site notes

This site is built on the [greenelab lab-website-template](https://github.com/greenelab/lab-website-template)
(the same template the TRIO Lab uses). Content is edited entirely through Markdown
and YAML — no HTML required.

## Where to edit things

- **Site name / links / social icons:** `_config.yaml`
- **Home page:** `index.md`
- **Research / publications page:** `research/index.md`
- **Projects & facilities:** page `projects/index.md`, data `_data/projects.yaml`
- **Team:** page `team/index.md`, one file per person in `_members/`
- **Teaching:** `teaching/index.md`
- **Blog posts:** one file per post in `_posts/` (named `YYYY-MM-DD-title.md`)
- **Contact:** `contact/index.md`
- **Publications list:** `_data/citations.yaml` (see note below)

## Adding a team member

Create `_members/first-last.md`:

```
---
name: First Last
image: images/photo.jpg      # or images/team/first-last.jpg once you add a photo
role: phd                    # principal-investigator | phd | masters | undergrad | visiting
description: Their research topic
links:
  github: handle
  linkedin: handle
---

Short bio.
```

Role labels/icons are defined in `_data/types.yaml`.

## Publications (automatic)

`_data/citations.yaml` is currently seeded by hand so the Research page renders
immediately. The template can also generate it **automatically**:

- `_data/orcid.yaml` is set to Dr. Nakka's ORCID (`0000-0001-7897-3644`).
- The included GitHub Action (`.github/workflows`) runs the `_cite` tool, which
  pulls works from ORCID + any DOIs in `_data/sources.yaml` and regenerates
  `_data/citations.yaml`. That run will overwrite the hand-seeded list with the
  full, up-to-date set.

## Photos

Member/PI photos couldn't be downloaded automatically. Drop image files into
`images/` (e.g. `images/team/`) and point each member's `image:` field at them.
Until then, a neutral fallback portrait with the role icon is shown.

## Run locally

```
bundle install
bundle exec jekyll serve
```

## Deploy (GitHub Pages)

IMPORTANT: the contents of this folder must be at the **repository root** — not
inside a subfolder. `.github/`, `_config.yaml`, and `index.md` must be top-level
in the repo, or GitHub's default build runs instead and fails.

1. Commit and push these files to the `main` branch of your repo.
2. Settings → Actions → General → allow workflows to run (if prompted).
3. The `on-push` workflow builds the site and pushes the result to a
   **`gh-pages`** branch (first run takes a couple of minutes).
4. Settings → Pages → Build and deployment → Source → **Deploy from a branch**,
   Branch → **`gh-pages`** → **/ (root)** → Save.
5. The site goes live at your Pages URL — for this repo name,
   `https://aerospaceroboticslab.github.io/`.
