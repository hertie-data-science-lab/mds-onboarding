# mds-onboarding

The **MDS First-Year Prep** site - a GH pages guide that helps incoming
Master of Data Science & AI (MDS) students at the [Hertie School Data Science Lab](https://github.com/hertie-data-science-lab)
prepare in **programming** and **mathematics** before the programme begins.

Live site: **https://hertie-data-science-lab.github.io/mds-onboarding/**

## What's here

| Page | File | Content |
| --- | --- | --- |
| Landing | `index.md` | Welcome, what students have access to, how to use the guide |
| Programming | `programming.md` | DataQuest paths, Python/R fundamentals, R-vs-Python |
| Mathematics | `mathematics.md` | Brilliant maths & stats classes, 3Blue1Brown |
| Further resources | `resources.md` | Optional, de-emphasised extras |

Navigation is defined in `_data/nav.yml`.

## Editing content

Edit the Markdown pages directly - content is separate from presentation. The visual
theme (layout, colours, components) is inherited from the shared
[`dsl-jekyll-theme`](https://github.com/hertie-data-science-lab/dsl-jekyll-theme) via
`remote_theme` in `_config.yml`; restyling happens there, not here.

**Yearly updates** live at the top of `_config.yml`:

- `brilliant_join_url` - the Brilliant link for both the Maths and Statistics cards.
  Currently the public course catalogue (no login). Swap in the current cohort's
  classroom invite (`.../classroom/join-v2/<id>`) to give students free Premium.
- `course_semester` - e.g. `2026 Entry`.

## Local preview

```bash
bundle install
bundle exec jekyll serve
# → http://localhost:4000/mds-onboarding/
```

`remote_theme` fetches the theme from GitHub at build time, so local builds need internet
(and the theme repo must be pushed).

## Deployment

`.github/workflows/deploy.yml` builds with Jekyll and deploys to GitHub Pages on every push
to `main`. It also rebuilds when the shared theme changes (via a `theme-updated`
repository dispatch) and weekly as a backstop. Enable **Settings → Pages → Source: GitHub
Actions**.
