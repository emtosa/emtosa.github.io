# aicliproductivity

A Jekyll-based GitHub Pages blog for CLI-first developer content.

---

## One-time local setup (optional preview)

```sh
gem install bundler jekyll
cd aicliproductivity
bundle init
bundle add jekyll minima jekyll-feed jekyll-seo-tag
bundle exec jekyll serve
# → http://localhost:4000
```

---

## Publish to GitHub Pages

### Step 1 — Create the remote repo

**Option A: via `gh` CLI (fastest)**
```sh
gh repo create aicliproductivity --public --description "CLI-first developer blog"
```

**Option B: via GitHub web UI**
1. Go to https://github.com/new
2. Name: `aicliproductivity`
3. Visibility: Public
4. Do NOT initialize with README (you already have one)
5. Click "Create repository"

> **Note:** If you want the blog at `https://yourusername.github.io` (root domain), name the repo `<yourusername>.github.io` instead.

---

### Step 2 — Set `url` and `baseurl` in `_config.yml` (do this before pushing)

Update these two lines in `_config.yml` before your first push:

```yaml
url: "https://YOUR_USERNAME.github.io"
baseurl: "/aicliproductivity"
```

> **⚠️ Important:** Leaving `url` or `baseurl` empty breaks RSS feed links and SEO
> canonical URLs. Jekyll's `jekyll-feed` and `jekyll-seo-tag` plugins use these
> values to generate absolute URLs — empty strings produce malformed `<link>` tags.

---

### Step 3 — Connect and push

```sh
cd aicliproductivity

# Add remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/aicliproductivity.git

# First commit (includes the url/baseurl you just set)
git add .
git commit -m "Initial blog setup with first post"

# Push
git push -u origin main
```

---

### Step 4 — Enable GitHub Pages

1. Go to your repo on GitHub
2. **Settings → Pages**
3. Under **Source**, select `Deploy from a branch`
4. Branch: `main`, folder: `/ (root)`
5. Click **Save**

GitHub will build and publish in ~1 minute.

Your site will be live at:
```
https://YOUR_USERNAME.github.io/aicliproductivity/
```

---

## Writing a new post

Use the helper script:

```sh
# Usage: ./scripts/new-post.sh "my-post-slug" "My Post Title"
./scripts/new-post.sh "shell-aliases-for-productivity" "Shell Aliases That Save Hours"
```

Then open the created file in `_posts/`, write your content, commit, and push:

```sh
git add _posts/
git commit -m "New post: Shell Aliases That Save Hours"
git push
```

GitHub Pages rebuilds automatically on every push to `main`.

---

## Editorial Coherence Checklist

Before publishing any post, confirm:

- [ ] Opening includes Hook -> Thesis -> Audience in the first ~120 words
- [ ] Scope is explicit (for example: "As of <month year>, directional analysis")
- [ ] Comparison lens is consistent across sections (capability/distribution/governance/economics)
- [ ] Claims use calibrated language ("likely", "currently", "depends on execution")
- [ ] Risks and disconfirming conditions are included
- [ ] Practical "what to do next" guidance is present for operators/builders
- [ ] Ending includes a concise decision checklist or litmus test
- [ ] Title, description, and tags match the post's actual scope

---

## Repo structure

```
aicliproductivity/
├── _config.yml          # Jekyll site config
├── index.md             # Home page (lists posts)
├── README.md            # This file
├── _posts/
│   └── 2026-05-29-ai-productivity-cli-developers.md
└── scripts/
    └── new-post.sh      # Low-friction post authoring helper
```
