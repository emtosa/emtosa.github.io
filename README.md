# emtosa.github.io

A Jekyll-based GitHub Pages **personal blog** for broad community writing.

---

## One-time local setup (optional preview)

```sh
gem install bundler jekyll
cd emtosa.github.io
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
gh repo create YOUR_USERNAME.github.io --public --description "Personal blog"
```

**Option B: via GitHub web UI**
1. Go to https://github.com/new
2. Name: `<yourusername>.github.io`
3. Visibility: Public
4. Do NOT initialize with README (you already have one)
5. Click "Create repository"

> **Note:** For root-domain publishing (`https://yourusername.github.io`), the repo **must** be named `<yourusername>.github.io`.

---

### Step 2 — Set `url` and `baseurl` in `_config.yml` (do this before pushing)

Update these two lines in `_config.yml` before your first push:

```yaml
url: "https://YOUR_USERNAME.github.io"
baseurl: ""
```

> **⚠️ Important:** `url` must be set correctly for RSS and canonical URLs.
> For `<username>.github.io` root-domain sites, `baseurl: ""` is expected.
> For project sites, set `baseurl` to the repo path (for example, `/my-project`).

---

### Step 3 — Connect and push

```sh
cd emtosa.github.io

# Add remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/YOUR_USERNAME.github.io.git

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
https://YOUR_USERNAME.github.io/
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
YOUR_USERNAME.github.io/
├── _config.yml          # Jekyll site config
├── index.md             # Home page (lists posts)
├── README.md            # This file
├── _posts/
│   └── 2026-05-29-microsoft-model-positioning.md
└── scripts/
    └── new-post.sh      # Low-friction post authoring helper
```
