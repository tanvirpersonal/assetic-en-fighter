# assetic-en-fighter

Web-hosted 3D assets for the fighter game, served with GitHub Pages.

- Live viewer: https://tanvirpersonal.github.io/assetic-en-fighter/
- 4K textures in the viewer: https://tanvirpersonal.github.io/assetic-en-fighter/?q=4k

## Layout

| Path | What it is |
| --- | --- |
| `index.html` | Viewer page, the site's front page |
| `models/<asset>/` | Web-ready model files: `.gltf`, `.bin`, and `textures/2k`, `textures/4k` |
| `lib/` | three.js r186 modules used by the viewer (works offline) |
| `source/` | Blender file and original EXR/AO maps. Not loaded by the site |
| `manifest.json` | Asset list with URLs, size and origin, for the game to read |
| `.nojekyll` | Tells GitHub Pages to serve every file as-is |

## Using an asset in the game

GitHub Pages sends `Access-Control-Allow-Origin: *`, so any page can load these files.

```js
import { GLTFLoader } from 'three/addons/loaders/GLTFLoader.js';

const BASE = 'https://tanvirpersonal.github.io/assetic-en-fighter/';
new GLTFLoader().load(BASE + 'models/gallinera_table/gallinera_table_2k.gltf', (gltf) => {
  scene.add(gltf.scene);
});
```

Use the `_2k` file on phones and the `_4k` file when quality matters more than download size.

## Gallinera table

Size 0.83 x 0.49 x 0.52 m, origin at the centre of the base on the floor, 5,528 triangles.
Parts: `gallinera_table`, `gallinera_table_door_a`, `gallinera_table_door_b`.
For a flat-top collider the table top is at y = 0.488.

## Adding a new asset

Put its `.gltf`, `.bin` and textures in `models/<name>/`, keep the originals in `source/`,
and add an entry to `manifest.json`.

## Turning Pages on

Repo Settings, Pages, Source: Deploy from a branch, branch `main`, folder `/ (root)`.
