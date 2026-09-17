# Portfolio site

Static site, no build step. Everything that gets deployed lives in `docs/` — the folder name GitHub Pages serves from.

```
docs/
  index.html          list of work
  cv.html             CV, with print styles for the PDF
  work/*.html         one page per project
  assets/css/cv.css      the whole site
  assets/img|pdf
  data/projects.json  data reference for the work list (the HTML is hand-written)
```

## Run locally

```bash
python3 -m http.server -d docs 8000
```

## Deploy

GitHub Pages, serving the `docs/` folder from the `main` branch. Pushing to `main` deploys.

## Regenerating the CV PDF

```bash
cd docs && python3 -m weasyprint cv.html assets/pdf/Uliana-Hrab-CV.pdf
```

## Note on `work/`

`work/` holds working copies of the source projects while they were being translated and
cleaned up. It is gitignored here — each project is published as its own repository. The
originals under `~/Projects` were never modified.
