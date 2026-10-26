# Gallinera table viewer

Run from this folder:

    python3 -m http.server 8000

Then open http://localhost:8000 (the page cannot be opened by double-clicking index.html,
browsers block loading the model from file://).

- `gallinera_table.gltf` / `.bin`: the model from the repo (texture paths pointed at `textures/`)
- `textures/`: 2K web versions of the diffuse, ARM (AO/roughness/metal) and normal maps.
  The repo's normal map was only an EXR, which browsers can't load, so it was converted to JPG.
- `lib/`: three.js r186 modules, bundled so the page works offline

Source model and original 4K textures stay in the repo root and `assets/`.
