# Portfolio website: Nihar Sandeep Bhave

A lightweight, static portfolio built with plain HTML, CSS and JavaScript. No build step, no frameworks, no external requests (fonts are bundled). It is ready to host on GitHub Pages.

## What's inside

```
portfolio/
├── index.html                 Page content, SEO tags and structured data
├── style.css                  All styling (colours and sizes are variables at the top)
├── script.js                  Mobile menu, active nav link, hero bar animation
├── .nojekyll                  Tells GitHub Pages to serve the files as they are
├── README.md
└── assets/
    ├── Nihar_Bhave_Resume.pdf   The resume the download buttons serve
    ├── favicon.svg
    ├── fonts/                   Inter (Regular, SemiBold, Bold), subset to Latin, WOFF2
    └── img/                     Project screenshots (WebP)
```

## Run it locally

Open `index.html` in a browser, or serve the folder so paths behave exactly as they will online:

```bash
cd portfolio
python3 -m http.server 8000
# then open http://localhost:8000
```

## Things to update

1. **Live Demo buttons.** A project card shows a Live Demo button only when a real, working demo exists. None of the three public repositories link to a deployed demo yet, so the cards currently show the GitHub button only. When you publish one, add this inside that project's `<div class="project-links">`, before the GitHub button, using the real address:

   ```html
   <a class="btn btn-primary btn-sm" href="PASTE-THE-REAL-DEMO-URL-HERE" target="_blank" rel="noopener noreferrer">Live Demo<span class="visually-hidden"> (opens in a new tab): project name</span></a>
   ```

   - Tableau dashboard: publish it to Tableau Public (File > Save to Tableau Public), then copy the address of the published dashboard.
   - Streamlit apps: deploy each one free at share.streamlit.io from its GitHub repository, then copy the `.streamlit.app` address.
2. **Resume.** To update it, replace `assets/Nihar_Bhave_Resume.pdf` and keep the same file name. All three download buttons pick it up.
3. **Screenshots.** Replace the files in `assets/img/` (keep the names, or update `src`, `width`, `height` and `alt` in `index.html`).
4. **Sample-data note.** The BI platform card says it was built on a sample dataset, because its screenshot shows a small demo dataset. Edit that line if you load something bigger.
5. **Attendance project.** It has no repository, so its card has no button and shows a diagram of how it works. If you upload it to GitHub later, add a button in a `project-links` block like the other cards.

## Deploy with GitHub Pages

You need a GitHub account (yours is `Nihar-Bhave`). There are two ways to host. Option A gives the cleanest URL.

### Option A: user site (recommended)

1. On GitHub, click **New repository**. Name it exactly **`Nihar-Bhave.github.io`**, set it to **Public**, and click **Create repository**. Do not add a README there.
2. In a terminal, from inside this folder:

   ```bash
   git init
   git add .
   git commit -m "Add portfolio website"
   git branch -M main
   git remote add origin https://github.com/Nihar-Bhave/Nihar-Bhave.github.io.git
   git push -u origin main
   ```

   (No Git installed? On the new repository page, click **uploading an existing file**, drag in everything from this folder, including the `assets` folder, and commit.)
3. Go to the repository's **Settings > Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose branch **main** and folder **/ (root)**, then click **Save**.
4. Wait one to three minutes and refresh the Pages settings screen. It will show the live address.

Final URL: **https://nihar-bhave.github.io/** (GitHub treats the repository name `Nihar-Bhave.github.io` and the lowercase address as the same site.)

### Option B: project site

Use any repository name, for example `portfolio`, and follow the same steps (replace the remote URL with `https://github.com/Nihar-Bhave/portfolio.git`).

Final URL: **https://nihar-bhave.github.io/portfolio/**

All paths in the site are relative, so both options work without changing any code.

## After it is live

- Open the live URL and click every link, both download buttons and the mobile menu (on your phone) once.
- Add your live URL to your resume, LinkedIn "Website" field and GitHub profile.
- The page already declares `https://nihar-bhave.github.io/` as its canonical address and uses `assets/img/og-card.png` as its link-preview image. If you host it at a different address (Option B), update the `canonical`, `og:url` and `og:image` tags in `index.html`.
- To check how a link will look when shared, paste your URL into LinkedIn's Post Inspector.

## Notes

- Colours live in the `:root` block at the top of `style.css`. Text and accent colours were chosen for readable contrast on the dark background.
- The page respects the "reduce motion" system setting. The only animation is the hero bar filling once on load.
- Inter is licensed under the SIL Open Font License.
