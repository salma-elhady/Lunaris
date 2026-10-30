# LUNARIS — Full-Stack Lunar Mission Intelligence Prototype

A responsive full-stack starter for the NASA Space Apps Challenge 2026 CLPS Lunar Mission Browser theme.

## Included
- Responsive cinematic frontend in HTML/CSS/JavaScript.
- Interactive schematic lunar map, selectable demo sites, scenario controls, comparison list and searchable 19-source research library.
- Python FastAPI backend and API docs.
- PostgreSQL/PostGIS Docker Compose configuration and SQLAlchemy model foundation.
- Scientific methods notes, roadmap, source CSV and tests.

## Scientific integrity
The map and site names are illustrative artwork, not georeferenced NASA data. Demo site records have no real coordinates. Quantitative solar and Earth-visibility calculations are deliberately marked unavailable until validated ephemerides, coordinate transformations and suitable terrain data are integrated. This is not ready for real mission planning.

## Run frontend
Open `frontend/index.html` in a browser. The frontend falls back to its local 19-source catalogue when the API is not running.

## Run backend (Python 3.10+)
```bash
cd backend
python -m venv .venv
# Windows: .venv\\Scripts\\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```
API docs: http://127.0.0.1:8000/docs

## Tests
```bash
cd backend
pytest
```

## Optional PostgreSQL/PostGIS
From project root: `docker compose up -d db`
The starter API runs without the database; persistence is not enabled by default.

## Next scientific steps
1. Download a small, documented NASA/PDS data subset.
2. Preserve product metadata, units, coordinate system, coverage and attribution.
3. Implement and validate terrain-aware illumination and Earth visibility calculations using appropriate SPICE kernels.
4. Compare against trusted reference cases and add regression tests.
5. Only mark a dataset integrated after the app actually processes it.
