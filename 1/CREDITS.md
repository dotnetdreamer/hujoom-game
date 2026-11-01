# Asset credits

Downloaded assets used by the game. Buildings, signage and audio are generated in code, except the
menu music.

- Environment textures: re-create with `node tools/env/fetch_textures.mjs` (add `--force` to refetch);
  the script verifies each download against the checksum or size published by its source and
  re-encodes the images at web-friendly sizes.
- Characters and animation: re-create with `python tools/assets/fetch_rocketbox.py` then
  `python tools/assets/build.py` (needs Blender 5.1), see the README.

## Characters and motion capture: Microsoft Rocketbox Avatar Library (MIT)

Avatars (meshes, skeletons, textures) and their motion-captured clips (walks, runs, idles, gestures,
cheering, sitting...) in `assets/characters/` are converted from
https://github.com/microsoft/Microsoft-Rocketbox (re-packed: facial bones folded into the head,
texture atlases, LODs, KTX2 compression; some textures recoloured or relabelled). The police
avatars' uniforms are repainted for the game (`tools/assets/uniform.py`) and the riot officers wear
the heads of other Rocketbox avatars (`Business_Male_05`, with `Police_Male_01`'s face as a variant).

> MIT License. Copyright (c) Microsoft Corporation.
> Permission is hereby granted, free of charge, to any person obtaining a copy of this software and
> associated documentation files (the "Software"), to deal in the Software without restriction,
> including without limitation the rights to use, copy, modify, merge, publish, distribute,
> sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is
> furnished to do so, subject to the following conditions: The above copyright notice and this
> permission notice shall be included in all copies or substantial portions of the Software.
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT
> NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
> NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES
> OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
> CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Fighting, falling and pushing motion: CMU Graphics Lab Motion Capture Database

The `cmu_*` clips in `anims.core.glb` and `anims.more.glb` are retargeted from http://mocap.cs.cmu.edu (see
`tools/assets/cmu/`). The data used in this project was obtained from mocap.cs.cmu.edu. The
database was created with funding from NSF EIA-0196217.

## Named characters

See `CREDITS-characters.md` for the Rocketbox bodies and heads behind the jailed leaders and the playable characters (invented people; no photographs).

## PBR texture sets: Poly Haven (CC0 1.0)

License: CC0 1.0 Universal (public domain), https://polyhaven.com/license.
Maps used: diffuse (albedo), OpenGL normal, ARM (ambient occlusion / roughness / metalness).

| Folder (`assets/env/textures/`) | Poly Haven asset | Author(s) | Source | Used for |
| --- | --- | --- | --- | --- |
| `asphalt/` | Asphalt Pit Lane (`asphalt_pit_lane`), 2K (ARM 1K) | Dimitrios Savva | https://polyhaven.com/a/asphalt_pit_lane | roads, bridge decks, markings base |
| `pavers/` | Concrete Pavers (`concrete_pavers`), 1K | Amal Kumar | https://polyhaven.com/a/concrete_pavers | chowks, plazas, sidewalks |
| `brickpave/` | Worn Brick Floor (`worn_brick_floor`), 1K | Amal Kumar | https://polyhaven.com/a/worn_brick_floor | old-city lanes and alleys |
| `dirt/` | Dirt (`dirt`), 1K | Charlotte Baglioni | https://polyhaven.com/a/dirt | bare earth, yards, fields, kerb dust, nullah bed |
| `grass/` | Sparse Grass (`sparse_grass`), 1K | Amal Kumar | https://polyhaven.com/a/sparse_grass | parks, medians, fields |
| `plaster/` | Painted Plaster Wall (`painted_plaster_wall`), 1K | Amal Kumar | https://polyhaven.com/a/painted_plaster_wall | painted building walls, landmarks |
| `brick/` | Large Red Bricks (`large_red_bricks`), 1K | Rob Tuytel | https://polyhaven.com/a/large_red_bricks | exposed brick walls |
| `concrete/` | Dirty Concrete (`dirty_concrete`), 1K | Rob Tuytel | https://polyhaven.com/a/dirty_concrete | kerbs, roofs, slabs, nullah embankments |
| `bark/` | Bark Willow 02 (`bark_willow_02`), 1K resampled to 512 | Charlotte Baglioni | https://polyhaven.com/a/bark_willow_02 | tree trunks and branches |

## Decals: ambientCG (CC0 1.0)

License: CC0 1.0 Universal (public domain), https://docs.ambientcg.com/license/.
Colour and opacity maps, resampled to at most 512 px.

| File (`assets/env/decals/`) | ambientCG asset | Source | Used for |
| --- | --- | --- | --- |
| `asphalt_damage_*` | Asphalt Damage 001 | https://ambientcg.com/a/AsphaltDamage001 | worn road patches |
| `manhole_a_*` | Manhole Cover 006 | https://ambientcg.com/a/ManholeCover006 | manhole covers |
| `manhole_b_*` | Manhole Cover 008 | https://ambientcg.com/a/ManholeCover008 | manhole covers |
| `leak_a_*` | Leaking 004 | https://ambientcg.com/a/Leaking004 | damp streaks on street walls |
| `leak_b_*` | Leaking 001 | https://ambientcg.com/a/Leaking001 | damp streaks on street walls |

## Leaf cards: ez-tree (MIT)

| File (`assets/env/trees/`) | Source | License |
| --- | --- | --- |
| `leaves_ash.png` | `src/lib/assets/leaves/ash_color.png` from the npm package `@dgreenheck/ez-tree@1.1.0` (https://github.com/dgreenheck/ez-tree) | MIT, Copyright (c) 2024 Daniel Greenheck |
| `leaves_oak.png` | `src/lib/assets/leaves/oak_color.png` from the same package | MIT, Copyright (c) 2024 Daniel Greenheck |

The tree branching code in `src/world/treeGen.ts` is a TypeScript port of the same project's
generator (MIT, Copyright (c) 2024 Daniel Greenheck); the licence text is reproduced in that file.

MIT License text (ez-tree):

> Permission is hereby granted, free of charge, to any person obtaining a copy of this software and
> associated documentation files (the "Software"), to deal in the Software without restriction, including
> without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
> copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the
> following conditions: The above copyright notice and this permission notice shall be included in all
> copies or substantial portions of the Software. THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF
> ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
> FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
> LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
> ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Menu music

`audio/hujoom-background.mp3` plays on the menus and under a chapter's intro. It was supplied by the
game's owner and re-encoded at 128 kbps for streaming (`ffmpeg -i <original> -map_metadata -1
-c:a libmp3lame -b:a 128k -ar 48000`).

## Gameplay music

`audio/crown-of-ash.mp3` loops during gameplay. The game's owner supplied it as `Crown of Ash.mp3`;
the original MP3 is streamed without re-encoding and follows the game's music volume and mute controls.
