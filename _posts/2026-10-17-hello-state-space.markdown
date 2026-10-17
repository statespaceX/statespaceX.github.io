---
layout: post
title: "Hello, State Space"
excerpt: "Welcome to the State Space blog — a starter post showing Markdown, LaTeX math, and code."
date: 2026-10-16 10:00:00
mathjax: true
---

Welcome to the **State Space blog**. This starter post shows the three things you'll use most: **Markdown**, **LaTeX math**, and **code**. Delete it once you've written your first real post.

## Markdown

Headers, *emphasis*, **bold**, [links](https://example.com), lists, quotes, tables, and images all work:

- Item one
- Item two with `inline code`

> A blockquote for highlighting key ideas.

| Model | Params | Notes |
|-------|--------|-------|
| Tiny  | 1M     | fast  |
| Base  | 100M   | solid |

<div class="imgcap">
<img src="{{ "/assets/rssicon.svg" | prepend: site.baseurl }}" width="60" alt="placeholder">
<br>
Captions work like this: wrap an image in a div with class "imgcap".
</div>

## LaTeX math

Set `mathjax: true` in the front matter (as this post does), then write inline math with `\\( ... \\)` and display math with `$$ ... $$`.

Inline example: \\( h_t = \tanh(W_{hh} h_{t-1} + W_{xh} x_t) \\) evolves the hidden state.

Display example:

$$ p(x) = \prod_{t=1}^{T} p(x_t \mid x_{<t}) $$

$$ \mathcal{L}(\theta) = -\mathbb{E}_{x \sim \mathcal{D}} \left[ \log p_\theta(x) \right] $$

**Tip:** always escape backslashes inside Markdown as `\\(`, and use double `$$` on their own lines for display equations. Avoid single `$...$` — it conflicts with Markdown.

## Code

Fenced code blocks get syntax highlighting via Rouge. Specify the language after the opening fence:

```python
import numpy as np

def rnn_step(h_prev, x_t, W_hh, W_xh):
    """One vanilla RNN step: h_t = tanh(W_hh h_{t-1} + W_xh x_t)."""
    return np.tanh(W_hh @ h_prev + W_xh @ x_t)

h = np.zeros(64)
for x_t in inputs:
    h = rnn_step(h, x_t, W_hh, W_xh)
```

```bash
bundle exec jekyll serve --livereload
```

Terminal-style blocks work too:

```text
$ bundle install
$ bundle exec jekyll serve
Server running at http://127.0.0.1:4000/
```

## Writing a new post

1. Copy this file to `_posts/YYYY-MM-DD-your-slug.markdown`
2. Update `title`, `excerpt`, and `date` in the front matter
3. Set `mathjax: true` only if the post uses LaTeX
4. Put images in `assets/<your-slug>/` and reference them as `/assets/<your-slug>/fig1.png`

Drafts in progress go in `_drafts/` (same format, no date in the filename) and preview with `bundle exec jekyll serve --drafts`.
