# hub

Central hub (static website) for Isaac Shinkle's firefighting, business, and photography resources.

## Cursor Cloud specific instructions

- This repo is a **static HTML site** with no build system, package manager, dependencies, tests, or linters. Files are plain `.html` (plus one PDF). There is nothing to install or compile.
- Structure: `index.html` (hub landing) links to `fire/`, `primitive/`, and `photography/`. `fire/` links to `nasdd/` (interactive Leaflet map), `daily-summary/` (serves `latest.pdf`), and `weekly-summary/`.
- Run it in development by serving the repo root over HTTP and opening the pages in a browser:
  - `python3 -m http.server 8000` (from the repo root), then visit `http://localhost:8000/`.
  - Serve from the repo root (not a subfolder) so relative links like `fire/nasdd/` resolve correctly.
- `fire/nasdd/index.html` loads Leaflet from the `unpkg.com` CDN and map tiles from OpenStreetMap, so the interactive map requires outbound network access to render.
- There is no "build" or "test" step. Verify changes by loading the affected page in the browser (and, for the NASDD page, confirming the map and markers render).
