# Kernel — emtosa.com

A Jekyll-based GitHub Pages technical-writing blog covering AI, productivity,
developer tools, and workflows. Live at **https://emtosa.com**.

## Stack

- Jekyll with the Minima theme
- `jekyll-feed` (RSS) and `jekyll-seo-tag` (meta tags) plugins
- Hosted on GitHub Pages (builds on push to `main`, no CI workflow needed)
- Custom domain: emtosa.com (CNAME)

## Local preview (optional)

```sh
gem install bundler jekyll
bundle exec jekyll serve
# → http://localhost:4000
```

## Writing a new post

Use the helper script:

```sh
./scripts/new-post.sh "my-post-slug" "My Post Title"
```

Then edit the created file in `_posts/`, commit, and push to `main`. GitHub
Pages rebuilds automatically.

## Editorial Coherence Checklist

Before publishing any post, confirm:

- [ ] Opening includes Hook → Thesis → Audience in the first ~120 words
- [ ] Scope is explicit (for example: "As of <month year>, directional analysis")
- [ ] Comparison lens is consistent across sections
- [ ] Claims use calibrated language ("likely", "currently", "depends on execution")
- [ ] Risks and disconfirming conditions are included
- [ ] Practical "what to do next" guidance is present
- [ ] Ending includes a concise decision checklist or litmus test
- [ ] Title, description, and tags match the post's actual scope

## Repo structure

```
emtosa.com/
├── _config.yml          # Jekyll site config (title, url, plugins)
├── _posts/              # 34 Markdown posts
├── assets/
│   └── images/          # OG image
├── scripts/
│   └── new-post.sh      # Low-friction post authoring helper
├── CNAME                # Custom domain: emtosa.com
├── index.md             # Home page (lists posts)
└── README.md            # This file
```