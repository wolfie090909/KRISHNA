# AGENTS.md

## Cursor Cloud specific instructions

This repository is a single static HTML landing page (`1`) with no build tools, no package manager, and no external dependencies.

### Serving the site

Run any static file server from the repo root. The simplest option:

```
python3 -m http.server 8080
```

Then open `http://localhost:8080/1` in a browser.

### Key notes

- The only source file is `/workspace/1` (an HTML file with inline CSS and JS).
- There is no linting, testing, or build step — the file is self-contained.
- The contact form uses a `window.alert()` stub; no backend or email service is wired up.
