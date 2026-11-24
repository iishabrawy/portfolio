# Ismael AlShabrawy — Portfolio

Modern single-page portfolio with **Liquid Glass** effects (translucent panels,
`backdrop-filter` blur + saturation, specular highlights, floating colour orbs)
and a **dark / light mode toggle** that remembers your choice and follows your
system setting by default.

Built from my CV: Senior iOS Engineer & Team Lead, 8+ years, 10+ apps, 1M+
downloads. Swift, SwiftUI, TCA, fintech — remote from Damietta, Egypt.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole portfolio — hero, about, experience, projects, skills, contact |
| `styles.css` | Liquid Glass styling + dark/light themes (`[data-theme="dark"]` / `"light"`) |
| `script.js` | Theme toggle, mobile menu, scroll-reveal, footer year |
| `Ismael-AlShabrawy-CV.pdf` | Downloadable CV linked from the site |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is |

No build step, no framework, no dependencies. Edit the HTML directly to change
any text, link or project.

## How to put it on GitHub (GitHub Pages, free)

### Option A — in the browser (no Git, ~5 minutes)

1. Go to [github.com/new](https://github.com/new) and create a repository.
   Suggested name: `portfolio` — or `<your-username>.github.io` if you want the
   short URL (see step 4). Make it **Public**.
2. On the new repo page click **uploading an existing file**, then drag in
   every file from this folder: `index.html`, `styles.css`, `script.js`,
   `Ismael-AlShabrawy-CV.pdf`, `.nojekyll`, `README.md`.
   > If `.nojekyll` is hidden on your computer, it's fine to skip it — the
   > site still works; it only matters if you later add folders starting
   > with an underscore.
3. Click **Commit changes**.
4. Go to **Settings → Pages** (left sidebar). Under **Build and deployment**,
   set **Source** to **Deploy from a branch**, branch **main**, folder
   **/ (root)**, then **Save**.
5. Wait about a minute, refresh the Pages settings — your link appears there:
   - Repo named `portfolio` → `https://<your-username>.github.io/portfolio/`
   - Repo named `<your-username>.github.io` → `https://<your-username>.github.io/`

### Option B — from your terminal (Git)

```bash
# 1. Go into this folder
cd portfolio

# 2. Start Git and add the files
git init
git add .
git commit -m "Add portfolio"

# 3. Create the repo on github.com/new first, then link it
#    (replace USERNAME and REPO with yours)
git branch -M main
git remote add origin https://github.com/USERNAME/REPO.git
git push -u origin main
```

Then do step 4 from Option A (Settings → Pages → Deploy from a branch → main → root).

## Updating it later

Edit a file, then either re-upload it on GitHub (Option A) or:

```bash
git add .
git commit -m "Update portfolio"
git push
```

GitHub Pages rebuilds automatically — changes are usually live within a minute.

## Dark / light mode

- The sun/moon button in the top-right nav switches themes.
- The choice is saved in the browser (`localStorage`, key `ismael-theme`).
- With no saved choice, it follows the visitor's system setting
  (`prefers-color-scheme`), defaulting to dark.
- The inline script in `<head>` applies the saved theme before first paint,
  so there's no flash of the wrong theme.
