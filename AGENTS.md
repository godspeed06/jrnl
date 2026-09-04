# Base44 Dev Environment

## What this project is

`jrnl` is a **command-line journaling tool** written in Python (Poetry-managed).
It is NOT a web application — there is no web server or HTTP API in the source.

Because the Base44 preview is a web iframe, the preview serves the project's
**mkdocs documentation site** (`mkdocs.yml`, `docs/`, `docs_theme/`) on port 3000.
The full Poetry environment is installed in the image, so the `jrnl` CLI is also
runnable inside the container.

## Running it

```bash
docker compose -f docker-compose.base44.yml up -d --build
```

- Web preview: http://localhost:3000/ (mkdocs docs site)
- jrnl CLI inside the container:
  ```bash
  docker compose -f docker-compose.base44.yml exec -T docs python -m jrnl --version
  ```
  (The `jrnl` console script is not on PATH because deps are installed with
  `--no-root`; use `python -m jrnl` instead.)

## How it's wired

- `Dockerfile.base44` — python:3.12-slim base, installs Poetry and all project
  deps (`poetry install --no-root`), so the image stays valid across source edits.
- `docker-compose.base44.yml` — bind-mounts the repo at `/app`, maps port 3000,
  runs `mkdocs serve --dev-addr 0.0.0.0:3000`. mkdocs watches `docs/`,
  `docs_theme/`, and `mkdocs.yml` for live reload.
- No external secrets are required (no DB, no external APIs).

## Verifying it works

```bash
# Service healthy
docker compose -f docker-compose.base44.yml ps
# Serves docs content
curl -sf http://localhost:3000/ | head -5
# External hostname (what the preview uses)
curl -sf -H "Host: external-preview.example.com" http://localhost:3000/ | head -5
```

## Running tests (optional, not needed for the preview)

```bash
docker compose -f docker-compose.base44.yml exec -T docs poetry run poe test-run
```
