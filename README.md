# karthiks3000.github.io

Personal site of Karthik Subramanian — hands-on engineering manager,
AI systems on AWS. Live at <https://karthiks3000.github.io>.

## Structure

- `index.html` — home: case studies, writing, talks, about, contact
- `case-studies/` — four architecture/leadership case studies
- `styles/site.css` — the entire stylesheet; no build step, no JavaScript
- `assets/` — profile photo, favicon, public resume PDF

## Local development

No install step:

    python3 -m http.server 8000

## Deploy

GitHub Pages serves the `master` branch root. Pushing to `master` is a deploy.
