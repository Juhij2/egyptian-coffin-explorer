# Coffin Viewer — 3D + NLP annotations (MVP)

Interactive 3D coffin. Rotate/zoom, click gold ◆ markers to open a side panel
with the spell text + NER-extracted entities linked to DemonBase.

## Run it
From this folder:
    python3 -m http.server 8000
then open  http://localhost:8000  in Chrome.
(A local server is required — browsers block loading the .glb from a plain file:// page.)

## Edit content
Everything you change lives in **annotations.js**:
- `DEMONBASE_BASE` — your real DemonBase base URL
- `HOTSPOTS[]` — one entry per clickable zone (position, spell, translation, entities)

## Place a hotspot on a real hieroglyph zone
1. Tick **Dev mode** (top-left).
2. Click the coffin where the hieroglyphs are — the 3D coordinates print bottom-left (and copy to clipboard).
3. Paste those into a hotspot's `position` in annotations.js. Refresh.

## Files
- index.html      the Three.js viewer (you rarely touch this)
- annotations.js  YOUR data — hotspots, spells, entities
- coffin.glb      the 3D model (~70 MB)
