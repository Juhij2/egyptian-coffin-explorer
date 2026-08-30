# Coffin Viewer: 3D + NLP annotations (MVP)

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

## Credits

3D model: **"Complete Coffin (AB118)"** by [The Egypt Centre](https://sketchfab.com/TheEgyptCentre),
[Swansea University](https://www.swansea.ac.uk/egypt-centre/), obtained from
[Sketchfab](https://sketchfab.com/3d-models/complete-coffin-ab118-0a339e6fe9a547298fa95fb846fa927e)
and licensed under [CC-BY-4.0](http://creativecommons.org/licenses/by/4.0/).

**Changes made to the original:** the distributed model used the deprecated
`KHR_materials_pbrSpecularGlossiness` extension, which current Three.js no longer supports.
It was converted to standard `pbrMetallicRoughness` (`coffin_mr.glb`). No geometry was altered.

Coffin Texts passages are drawn from the [Thesaurus Linguae Aegyptiae](https://thesaurus-linguae-aegyptiae.de/).
Entity classification data comes from DemonBase (DemonThings project).

The viewer, the hotspot mapping, the NER extraction and the DemonBase linking are by Juhi Jadhav.
