# emtosa.com

Personal space for projects and notes.

This is a small static personal website. It uses local HTML and CSS, with no
JavaScript, external assets, analytics, forms or account integrations.

## Files

- `index.html`: personal homepage.
- `404.html`: missing-page response with a link to the homepage.
- `style.css`: shared responsive styles, including light and dark appearances.
- `CNAME`: custom domain, `emtosa.com`.
- `.nojekyll`: serves the static files directly.

## Preview

Run `python3 -m http.server 8000` from the repository, then visit
`http://localhost:8000`. Visit `/404.html` to preview the missing-page design;
Python's simple server does not use a custom 404 page automatically.

## Hosting

GitHub Pages serves this repository from the root of `main`. The custom domain
must have a valid TLS certificate before HTTPS can be enforced. Retired routes
have no redirect files; GitHub Pages serves `404.html` for missing pages.

## Personal boundary

Keep the website and repository exclusively personal. Use a personal Git identity
for contributions. Do not introduce business branding, business redirects,
tracking or account integrations without explicit owner direction.
