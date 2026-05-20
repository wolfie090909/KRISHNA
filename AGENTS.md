# AGENTS.md

## Cursor Cloud specific instructions

This repository is a single static HTML landing page (`1`) with no build tools, no package manager, and no external dependencies.

### Serving the site

The source file is `/workspace/1` (no `.html` extension), so `python3 -m http.server` will serve it as `application/octet-stream` and browsers won't render it. Use the custom server snippet below instead:

```bash
python3 -c "
import http.server, os

class Handler(http.server.SimpleHTTPRequestHandler):
    def guess_type(self, path):
        if os.path.basename(path) == '1':
            return 'text/html'
        return super().guess_type(path)

http.server.HTTPServer(('', 8080), Handler).serve_forever()
"
```

Then open `http://localhost:8080/1` in a browser.

### Key notes

- The only source file is `/workspace/1` (an HTML file with inline CSS and JS, but **no `.html` extension** — see serving note above).
- There is no linting, testing, or build step — the file is self-contained.
- The contact form uses a `window.alert()` stub; no backend or email service is wired up.
