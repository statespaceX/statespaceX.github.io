# State Space blog

Minimal Jekyll blog in the style of [karpathy.github.io](https://karpathy.github.io), ready for GitHub Pages. Write posts in Markdown with LaTeX math (MathJax) and syntax-highlighted code (Rouge).

## Quick start

```bash
bundle install
bundle exec jekyll serve --livereload
# preview at http://127.0.0.1:4000/
```

Show drafts too with `bundle exec jekyll serve --drafts`.

## New post

Copy the starter post and edit the front matter:

```bash
cp _posts/2026-10-17-hello-state-space.markdown _posts/2026-10-18-my-topic.markdown
```

```yaml
---
layout: post
title: "Your title"
excerpt: "One-line summary shown on the homepage."
date: 2026-10-18 12:00:00
mathjax: true   # only if the post uses LaTeX
---
```

Conventions:

- Posts live in `_posts/` as `YYYY-MM-DD-slug.markdown`
- Images go in `assets/<slug>/`, referenced as `/assets/<slug>/fig1.png`
- Drafts go in `_drafts/` (no date in filename)
- Inline math: `\\( ... \\)`, display math: `$$ ... $$` on its own lines
- Code: fenced blocks with a language, e.g. ` ```python `

## Deploy on GitHub Pages

1. Push this repo so Jekyll files are at the repo root
2. Repo Settings → Pages → Deploy from branch → `main` / `/ (root)`
3. Set `url` and `baseurl` in `_config.yml`:
   - User/org site (`statespacex.github.io`): `url: "https://statespacex.github.io"`, `baseurl: ""`
   - Project site (`statespacex.github.io/statespaceX`): `url: "https://statespacex.github.io"`, `baseurl: "/statespaceX"`

## Structure

```text
_config.yml        site title, url, markdown/highlighter settings
index.html         homepage listing all posts
feed.xml           RSS feed
about.md           about page (linked in nav via `includelink: true`)
_layouts/          default, post, page templates
_includes/         head, header, footer, mathjax partials
css/main.css       stylesheet (posts list, post, code, responsive)
assets/            images per post + rssicon.svg
_posts/            published posts
_drafts/           work in progress (not published)
```
