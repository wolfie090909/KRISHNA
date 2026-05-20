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
- **Browser MIME-type gotcha:** Python's `http.server` serves the file `1` as `application/octet-stream` (no `.html` extension), so browsers may download it instead of rendering. To work around this, either access `http://localhost:8080/1` and manually set Chrome to open it, or create a temporary symlink: `ln -sf 1 index.html` and navigate to `http://localhost:8080/index.html`.
