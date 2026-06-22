# webpage-csur-wot-search-engine

Public landing page for the ACM Computing Surveys paper "Searching the Web of Things: State of the Art, Challenges, and Solutions" (Tran, Sheng, Babar & Yao, CSUR Vol. 50, No. 4, pp. 1–34, 2017).

Hosted via GitHub Pages at: `https://nguyentran0212.github.io/webpage-csur-wot-search-engine/`

## Layout

- `index.md` — page content (Markdown, processed by Jekyll)
- `_layouts/default.html` — base HTML template
- `assets/css/style.css` — single stylesheet
- `assets/pdf/CSUR_WoTSE_NguyenTran.pdf` — downloadable copy of the paper
- `assets/figures/` — five figures converted from the paper (application, Metapath, Architecture, AnalyticalFramework, supportdimension)
- `_config.yml` — site config (`baseurl` set to `/webpage-csur-wot-search-engine`)
- `Gemfile` — Jekyll dependency pinned to `~> 4.3`

## Local preview

Requires Ruby + Bundler.

```bash
bundle install
bundle exec jekyll serve --host 127.0.0.1 --port 4002
# → http://127.0.0.1:4002/webpage-csur-wot-search-engine/
```

## Editing content

The page is one Markdown file. Sections (in order):
Hero → TL;DR → At a glance → Motivation → Meta-path & architecture → Research method → Findings → Open issues → Abstract → Cite.

`baseurl` in `_config.yml` is set to `/webpage-csur-wot-search-engine`. If you ever move this to a custom domain or root, set `baseurl: ""` and `url: "https://yourdomain.com"`.
