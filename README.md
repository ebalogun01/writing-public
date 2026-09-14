# writing-public

The published site: <https://ebalogun01.github.io/writing-public>

Essays on math, engineering, and the ideas underneath them. Built with [Jekyll]
and the [Just the Docs] theme, deployed to GitHub Pages by
`.github/workflows/pages.yml` on every push to `main`.

Drafting happens in a separate private repo. Only finished pieces land here.

## Layout

```
index.md                      home page + post index
nerdy-letters/
  index.md                    series landing page
  reteaching-math-1.md        Part 1 — Understanding dy/dx
assets/images/                figures (SVG)
_includes/head_custom.html    MathJax v3 config + figure styles
_config.yml                   site config
```

## Writing math

MathJax v3 is loaded site-wide. Kramdown emits `\(…\)` for inline math and
`\[…\]` for display math, and the config in `_includes/head_custom.html` matches
both (plus `$$…$$`).

- **Inline:** write `\\(dy/dx\\)` — the doubled backslash survives kramdown's
  escaping and reaches the browser as `\(dy/dx\)`.
- **Display:** fence with `$$` on its own line, above and below.

A single backslash renders as a literal paren. If math appears as raw text on
the live page, that is nearly always the cause.

## Figures

Hand-written SVG in `assets/images/`, embedded with a `<figure>` block:

```html
<figure>
  <img src="{{ site.baseurl }}/assets/images/ramp.svg" alt="...">
</figure>
```

The `{{ site.baseurl }}` prefix is required — the site is served from a
subpath, so root-relative `/assets/...` paths 404. Keep `alt` text in sync when
a figure is redrawn.

## Adding a post

1. Add the `.md` file to the relevant series folder.
2. Front matter: `title`, `parent`, `layout: default`, `nav_order`, `permalink`,
   `description`.
3. Link it from `index.md`.

## Local preview

```sh
bundle install
bundle exec jekyll serve   # http://localhost:4000/writing-public/
```

## Cross-posting

The canonical version of each essay lives here. Import into Medium and Substack
from the published page URL rather than pasting, so the canonical link points
back to this site. Neither platform runs MathJax — equations need to go over as
images.

[Jekyll]: https://jekyllrb.com
[Just the Docs]: https://just-the-docs.com
