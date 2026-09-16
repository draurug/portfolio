# Portfolio site

Static site, no build step. Everything that gets deployed lives in `site/`.

```
site/
  index.html          list of work
  cv.html             CV, with print styles for the PDF
  work/*.html         one page per project
  assets/css|img|pdf
  data/projects.json  data reference for the work list (the HTML is hand-written)
```

## Run locally

```bash
python3 -m http.server -d site 8000
```

## Deploy

Cloudflare Pages, connected to this repository:

- Build command: *(empty)*
- Build output directory: `site`

## Regenerating the CV PDF

```bash
chromium --headless --print-to-pdf=site/assets/pdf/Uliana-Hrab-CV.pdf \
         --no-pdf-header-footer http://localhost:8000/cv.html
```

## Note on `work/`

`work/` holds working copies of the source projects while they were being translated and
cleaned up. It is gitignored here — each project is published as its own repository. The
originals under `~/Projects` were never modified.
