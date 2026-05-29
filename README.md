# ai-cli-productivity-blog

A Jekyll-based GitHub Pages blog for CLI-first developer content.

---

## One-time local setup (optional preview)

```sh
gem install bundler jekyll
cd ai-cli-productivity-blog
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
gh repo create ai-cli-productivity-blog --public --description "CLI-first developer blog"
```

**Option B: via GitHub web UI**
1. Go to https://github.com/new
2. Name: `ai-cli-productivity-blog`
3. Visibility: Public
4. Do NOT initialize with README (you already have one)
5. Click "Create repository"

> **Note:** If you want the blog at `https://yourusername.github.io` (root domain), name the repo `<yourusername>.github.io` instead.

---

### Step 2 — Connect and push

```sh
cd /Users/tosao/ai-cli-productivity-blog

# Add remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/ai-cli-productivity-blog.git

# First commit
git add .
git commit -m "Initial blog setup with first post"

# Push
git push -u origin main
```

---

### Step 3 — Enable GitHub Pages

1. Go to your repo on GitHub
2. **Settings → Pages**
3. Under **Source**, select `Deploy from a branch`
4. Branch: `main`, folder: `/ (root)`
5. Click **Save**

GitHub will build and publish in ~1 minute.

Your site will be live at:
```
https://YOUR_USERNAME.github.io/ai-cli-productivity-blog/
```

---

### Step 4 — Update `_config.yml`

Once you have the live URL, update these two lines in `_config.yml`:

```yaml
url: "https://YOUR_USERNAME.github.io"
baseurl: "/ai-cli-productivity-blog"
```

Then commit and push:
```sh
git add _config.yml
git commit -m "Set live site URL in config"
git push
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

## Repo structure

```
ai-cli-productivity-blog/
├── _config.yml          # Jekyll site config
├── index.md             # Home page (lists posts)
├── README.md            # This file
├── _posts/
│   └── 2025-07-15-ai-productivity-cli-developers.md
└── scripts/
    └── new-post.sh      # Low-friction post authoring helper
```
