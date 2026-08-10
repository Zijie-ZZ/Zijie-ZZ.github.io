# Personal Academic Website

A simple, static personal academic website (plain HTML/CSS, no build step,
no JavaScript) designed for GitHub Pages.

## File structure

```
academic-website/
├── index.html          # Home — hero, research highlights, profile links
├── research.html       # Research interests and project descriptions
├── publications.html   # Selected publications
├── cv.html             # CV download page
├── photos.html         # Photo gallery (travel, conferences, fieldwork)
├── contact.html        # Contact information
├── css/
│   └── style.css       # All styling (colors, layout, responsive rules)
├── assets/
│   ├── Zijie_Zheng_CV.pdf        # Your CV (still a placeholder)
│   ├── _news-section.html.txt    # Parked News markup, not served
│   └── images/
│       ├── profile.jpg           # Headshot used on the home page
│       ├── highlight-*.png       # Home-page research highlight figures
│       └── photos/               # Gallery images
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
- **Research highlights** — each is one `<section class="highlight">` block
  in `index.html`: a figure from `assets/images/`, a title, and a short
  plain-language explanation.
- **Photos** — drop resized images into `assets/images/photos/`, then copy
  the `<figure class="photo-item">` template from the comment in
  `photos.html`. Resize first with `sips -Z 1600 photo.jpg`.
- **News** — the home-page News section is currently removed. Its markup is
  parked in `assets/_news-section.html.txt`; paste it back before `</main>`
  in `index.html` to restore it. The CSS is still in place.
- **CV** — currently hidden. `cv.html` still exists but is unlinked and
  carries a `noindex` tag. To bring it back: drop the `robots` meta from
  `cv.html`, add `<a href="cv.html">CV</a>` to the `<nav>` in all six
  pages, and uncomment the CV button in `index.html`. Put the actual PDF
  at `assets/Zijie_Zheng_CV.pdf` first — that link is still unresolved.
- **Accent color** — edit `--accent` and `--accent-dark` at the top of
  `css/style.css`.
- **Navigation** — the header nav is repeated in each page; if you add a
  page, add its link to the `<nav>` in all six files.

## Previewing locally

Open any `.html` file directly in a browser, or run a tiny local server:

```bash
cd academic-website
python3 -m http.server 8000
# then open http://localhost:8000
```
