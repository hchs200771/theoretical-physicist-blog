# Yi-Hsien (Sherry) Du — Academic Personal Site

**Live:** https://hchs200771.github.io/theoretical-physicist-blog/

A single-page static website. No framework, no build step — just `index.html` + `style.css`.

```
theoretical-physicist-blog/
├── index.html      # all content + a few lines of JS (theme toggle)
├── style.css       # all styling, light/dark via [data-theme]
└── photo.jpg       # the talk photo shown in the hero (pulled from the live site)
```

## Content notes

- **Photo, publications (9 papers), author lists, journals, arXiv links, Google Scholar and ORCID** are all pulled from the live Google Sites page and already filled in.
- **Optional:** to add a CV, drop a `cv.pdf` in this folder and add a `<a href="cv.pdf" ... class="pill">CV (PDF)</a>` line inside `hero__links` in `index.html`.

## Preview locally

Just double-click `index.html`, or serve it:

```bash
# Python (built into macOS)
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy to GitHub Pages

### One-time setup

1. Create a new GitHub repository (e.g. `yi-hsien-du.github.io` for a user site, or any name for a project site).
2. Push these files to the repo root:

   ```bash
   cd theoretical-physicist-blog
   git init
   git add .
   git commit -m "Initial academic site"
   git branch -M main
   git remote add origin https://github.com/<username>/<repo>.git
   git push -u origin main
   ```

3. On GitHub: **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Set branch to **`main`** and folder to **`/ (root)`**, then **Save**.
6. Wait ~1 minute. Your site goes live at:
   - `https://<username>.github.io/` — if the repo is named `<username>.github.io`
   - `https://<username>.github.io/<repo>/` — for any other repo name

### Updating the site later

Edit the files, then:

```bash
git add .
git commit -m "Update publications"
git push
```

GitHub Pages redeploys automatically within a minute.

## Custom domain (optional)

To use e.g. `www.yourdomain.com`:

1. In **Settings → Pages → Custom domain**, enter your domain and save (this commits a `CNAME` file).
2. At your domain registrar, add a `CNAME` DNS record pointing `www` to `<username>.github.io`.
3. Once DNS propagates, tick **Enforce HTTPS**.

---

Alternative hosts (same static files, zero config): **Netlify** or **Cloudflare Pages** — drag the folder in, or connect the GitHub repo.
