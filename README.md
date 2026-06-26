# menawhalen.com — Jekyll site for GitHub Pages

## What's in here
A minimal custom Jekyll site (no third-party theme gem) with:
- `index.md`, `about.md`, `research.md`, `courses.md`, `cv.md` — edit these directly, they're plain Markdown with simple front matter
- `courses/stat103.md` — example course subpage; copy this pattern to add more courses
- `_layouts/default.html`, `_includes/nav.html`, `_includes/footer.html` — the shared page shell
- `assets/css/style.css` — all styling lives here
- `CNAME` — already set to `menawhalen.com` so GitHub Pages knows your custom domain
- `cv/PUT_YOUR_CV_HERE.txt` — replace with your actual `current_CV.pdf`

## How to publish it

1. **Create the repo on GitHub** named exactly `menawhalen.github.io` (this exact name is what makes GitHub Pages serve it from the domain root automatically).

2. **Push this folder's contents to that repo's `main` branch.** From inside this folder:
   ```
   git init
   git add .
   git commit -m "Initial Jekyll site"
   git branch -M main
   git remote add origin https://github.com/menawhalen/menawhalen.github.io.git
   git push -u origin main
   ```

3. **Turn on GitHub Pages:** repo → Settings → Pages → under "Build and deployment," Source = "Deploy from a branch," Branch = `main`, Folder = `/(root)` → Save.

4. **Custom domain:** in that same Pages settings page, under "Custom domain," enter `menawhalen.com` and save (the `CNAME` file is already in the repo, so this should just confirm it). Wait for the DNS check to go green, then check "Enforce HTTPS."

5. **Your Porkbun DNS is already set correctly** from earlier (A records pointing at GitHub Pages' IPs, `www` CNAME) — no changes needed there.

## Before you push
- Swap in your real bio text on `about.md`, real research entries on `research.md`, and your actual CV PDF in `/cv/`.
- Add a `favicon.ico` to `assets/images/` if you want a custom tab icon (referenced already in the layout).
- Add more courses by duplicating `courses/stat103.md` and updating the `permalink`.

## Local preview (optional)
If you want to preview before pushing and have Ruby installed:
```
bundle install
bundle exec jekyll serve
```
Then visit `http://localhost:4000`. This step is optional — GitHub Pages will build the site for you automatically on push either way.
