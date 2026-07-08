# Personal Academic Website

A simple, static personal academic website (plain HTML/CSS, no build step,
no JavaScript) designed for GitHub Pages.

## File structure

```
academic-website/
├── index.html          # Home — name, tagline, bio, profile links
├── research.html       # Research interests and project descriptions
├── publications.html   # Selected publications
├── cv.html             # CV download page
├── contact.html        # Contact information
├── css/
│   └── style.css       # All styling (colors, layout, responsive rules)
├── assets/
│   ├── Zijie_Zheng_CV.pdf   # Your CV (replace the placeholder)
│   └── images/              # Photos and figures, if needed later
└── README.md
```

## Deploying to GitHub Pages

### Option A — user site (recommended): `https://<username>.github.io`

1. Create a **public** GitHub repository named exactly `<username>.github.io`
   (e.g. `zijiezheng.github.io`).
2. Push the contents of this folder to the repository root:

   ```bash
   cd academic-website
   git init
   git add .
   git commit -m "Initial website"
   git branch -M main
   git remote add origin https://github.com/<username>/<username>.github.io.git
   git push -u origin main
   ```

3. On GitHub: **Settings → Pages → Build and deployment**, set
   **Source: Deploy from a branch**, branch `main`, folder `/ (root)`.
4. Wait a minute or two, then visit `https://<username>.github.io`.

### Option B — project site: `https://<username>.github.io/<repo-name>`

Same steps, but the repository can have any name. The site will live at
`https://<username>.github.io/<repo-name>`. All links in this site are
relative, so no changes are needed.

## Editing the site

Everything is plain HTML — edit the text directly in each page.

- **Profile links** — search for `EDIT` comments in `index.html` and
  `contact.html`, then replace the `#` placeholders with your real
  Google Scholar / ORCID / LinkedIn / GitHub URLs.
- **CV** — put your PDF at `assets/Zijie_Zheng_CV.pdf` (or change the
  filename in `index.html` and `cv.html`).
- **Publications** — each entry in `publications.html` is one
  `<div class="publication">` block. Copy, paste, and edit the three
  lines inside. Delete the placeholder entries once real ones are added.
- **Accent color** — edit `--accent` and `--accent-dark` at the top of
  `css/style.css`.
- **Navigation** — the header nav is repeated in each page; if you add a
  page, add its link to the `<nav>` in all five files.

## Previewing locally

Open any `.html` file directly in a browser, or run a tiny local server:

```bash
cd academic-website
python3 -m http.server 8000
# then open http://localhost:8000
```
