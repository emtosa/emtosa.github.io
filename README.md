# emtosa.com

> **This site is redirect-only.** As of 2026-07-29, emtosa.com has been
> consolidated into **noraze.com**. All pages serve a meta-refresh redirect
> to the equivalent path on noraze.com with `noindex`. The 34 blog posts
> were migrated to noraze.com. This repo remains as the redirect host.

## Content

emtosa.com was a Jekyll-based GitHub Pages technical-writing blog covering
AI, productivity, developer tools, and workflows. The content pillars were
Copilot / agentic AI, Azure / Spark / Kafka data engineering, SwiftUI /
iOS / App Store product engineering, and deep-work / autonomy systems.

## Redirect behavior

Every HTML page contains:

```html
<meta http-equiv="refresh" content="0; url=https://noraze.com/<equivalent-path>/">
```

Plus `<link rel="canonical">` and `noindex` directives pointing to
noraze.com.

## Repo structure

```
emtosa.com/
├── index.html           # Redirect to noraze.com/
├── _posts/              # 34 Markdown posts (archived, not served)
├── blog/                # Redirect-only HTML pages
├── feed/                # Redirect-only RSS
├── search/              # Redirect-only search
├── CNAME                # Custom domain: emtosa.com
├── _config.yml          # Jekyll site config (archived)
└── README.md            # This file
```

## Notes

- The Jekyll build artifacts (`_site/`, `.jekyll-cache/`) are gitignored
  and not deployed. GitHub Pages serves the static redirect HTML directly.
- The blog posts in `_posts/` are preserved as an archive but are not
  rendered by Jekyll anymore (the pages in `blog/` are static redirect HTML).
- Active content lives at **noraze.com** (repo: `foculoom/noraze.com`).