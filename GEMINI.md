# GEMINI.md — Persistent Context & Memory for Gemini

## Project Summary
- **Repository**: `banana-cad`
- **Application**: Banana CAD — Zero-dependency 3D Parametric CAD & Simulation Studio
- **Primary Executable Entrypoint**: [`index.html`](file:///Users/tajparekh/documents/hackathon/banana-cad/index.html) (mirrored to `bananaCAD_unified.html`)
- **Architecture**: Single self-contained file. Executable natively offline via `file://` in any browser as well as via `http(s)://` web servers. No bundler, no npm build step, and no external CDN dependencies (pure vanilla Canvas 2D projection mathematics).

---

## Origin & Unification History
Banana CAD evolved across 6 hackathon iterations that were consolidated into `index.html`:
1. `bananaCADv1.html`: Foundational 3D CAD engine (depth-sorting painter's algorithm, orbit/pan/zoom, auth, projects grid, CSG fuse/group, bounce test mode, STL export/import).
2. `banana_cad_v2.html`: Real-time measurement calipers (`drawMeasurementGuides()`, `#dimensionPanel`, `#dimX`, `#dimY`, `#dimZ`) and negative / subtractive geometry (`#negativeToggleBtn`, `#negativeBadge`).
3. `bananaCADv3.html`: Precision magnetic snapping system (`#snapPanel` for move, rotate, scale) and guest tier restrictions (`#guestBanner`, `#guestBadge`, `#loginRequiredModal`).
4. `bananaCAD_v4.html`: Categorized shape modal (`#shapeModal`), search filter, plate variations, custom builds library (`#saveBuildBtn`, `bananacad_builds`), and drag-to-canvas spawning (`#dragGhost`).
5. `bananaCADv5.html`: Gear meshing physics simulation, speed controls (`#gearPanel`, `#gearSpeedSlider`, `#gearSpinToggle`), counter-rotation ratio calculations, and `#gearBadge`.
6. `deepseek_html_20261011_d2324b (6).html`: Smart 2D sketch canvas overlay (`#sketchOverlayCanvas`, `#sketchBtn`, `#sketchPanel`), closed contour recognition, and extrusion to 3D prism solids.

---

## Technical Architecture & Design Decisions
- **Rendering Engine**: Custom 3D wireframe and solid polygon renderer built on HTML5 Canvas 2D using Euler rotation matrices, perspective projection, and painter's depth sorting. Zero Three.js or WebGL dependencies required.
- **Routing**: Single-page hash routing (`window.addEventListener('hashchange', ...)`) handling:
  - `#/auth`: User account login, registration, and guest mode switcher.
  - `#/projects`: Project manager, template chooser, import STL/JSON, search, deletion.
  - `#/editor`: Full 3D CAD studio workspace with all panels and canvas hud.
- **Safe Storage**: LocalStorage wrapped in `try/catch` fallbacks to ensure compatibility with private browsing, sandbox iframes, or environments where storage is restricted:
  - `bananacad_user`: Current logged-in user profile or null.
  - `bananacad_projects`: Array of user projects containing shape definitions.
  - `bananacad_builds`: Array of user-saved custom composite assemblies.

---

## Critical Invariants & Rules for Future Sessions
1. **Never Break Single-File Integrity**: Any new feature or bugfix must be directly integrated into `index.html` (and kept in sync with `bananaCAD_unified.html`).
2. **Zero External Dependencies**: Do not insert `<script src="...">` tags pointing to external CDNs. All math, geometry, and simulation logic must remain self-contained.
3. **Double-Click Executable**: `index.html` must always be runnable by double-clicking it directly in macOS Finder (`file://`).
4. **Validation Routine**: Always verify JavaScript syntax using:
   ```bash
   node -e "const fs = require('fs'); const html = fs.readFileSync('index.html', 'utf8'); const m = html.match(/<script>([\s\S]*?)<\/script>/); if (!m) process.exit(1); eval('function __check() {' + m[1] + '}');"
   ```
