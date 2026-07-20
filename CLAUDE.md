# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Karthik Subramanian's personal portfolio site, served by GitHub Pages from the
`master` branch root at karthiks3000.github.io. **Pushing to `master` deploys
immediately** — do feature work on a branch and merge only when the user
approves.

Plain multi-page HTML/CSS: no build step, no JavaScript (the JSON-LD block in
index.html is structured data, not code), no external fonts or CDNs. All
styling lives in `styles/site.css` (design tokens at the top; light/dark via
`prefers-color-scheme`).

## Layout

- `index.html` + `case-studies/*.html` — content pages sharing the
  `.entry`/`.rail`/`.body` margin-annotated grid pattern from `site.css`
- `resume/`, `docs/superpowers/`, `consistency-checklist.md` — local-only
  private working files (gitignored): resume sources + build tooling, design
  specs/plans, and the identity-consistency checklist. They exist on disk but
  must never be committed to this public repo.

## Hard rules

- **Private files**: `*.docx`, `resume/`, and `docs/superpowers/` are
  gitignored on purpose — performance reviews and application strategy must
  never be committed. Never `git add -A`; add files by explicit path.
- Resumes contain no phone number by design; the site-hosted PDF is the EM
  variant (`assets/resume-karthik-subramanian.pdf`, copied from
  `resume/out/`).
- The canonical job title everywhere is "Senior Software Engineering Manager".
- Every dollar figure keeps its label (projected / realized / avoided /
  returned) and must match `resume/facts.md`.
- Resume edits: change `resume/resume-em.md` and `resume/resume-tl.md`
  together (same facts, different ordering), then rerun `./resume/build.sh`
  and re-copy the public PDF to `assets/` if it changed.

## Verifying changes

    python3 -m http.server 8000

Check pages in a real browser; there is no test suite. For resume changes,
verify the PDFs are exactly 2 pages:
`mdls -name kMDItemNumberOfPages -raw resume/out/*.pdf`
