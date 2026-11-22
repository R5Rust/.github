# R5Rust

A from-scratch **Rust** reimplementation of Apex Legends' Firing Range: rendering, lighting, collision, movement,
weapons and ziplines ported from the game's own decompiled code and shaders, and measured against R5Flowstate.
No game assets are distributed; everything is extracted from your own Apex install.

![Firing Range](img/range.jpg)

| | |
|---|---|
| ![Town](img/town.jpg) | ![Overview](img/overview.jpg) |

## Repositories

| Repo | What |
|---|---|
| [R5Rust](https://github.com/R5Rust/R5Rust) | The game: wgpu client, dedicated server stub, shared movement sim, docs on every ported system |
| [launcher](https://github.com/R5Rust/launcher) | The desktop launcher: install from your Apex files, modes + maps, video settings, patch notes, mods (coming) |
| [export-map](https://github.com/R5Rust/export-map) | Builds map data (geometry, real collision, lighting lumps, cubemaps, materials) from your own Apex install |
| [r5f-probe](https://github.com/R5Rust/r5f-probe) | Ground truth: plays scripted inputs and camera poses in real R5Flowstate and logs/screenshots them |
| [docs](https://github.com/R5Rust/docs) | How the Apex mechanics work and how R5Rust reproduces them: movement so far |

## Where it is

- **Rendering:** the current retail map and materials with the S30 shader code: lightmaps, light probes, cubemaps,
  cascaded sun shadows, triplanar rock blending, HDR sky + sun, auto exposure, bloom, grading LUT, static-prop fade
  and LOD rules, loot highlights.
- **Movement:** Apex's PlayerMove / walk / air / duck / slide / step / mantle, wall climb + wall jump and the lurch,
  ported from the binary; walk, sprint, jumps, slides and lurches track real R5Flowstate within a few u/s.
- **Ziplines:** the map's zipline entities with the game's use search, mount, ride and detach rules and the
  zipline use prompt.
- **Weapons + loot:** R-99 in first person (viewmodel animation, recoil spring, sounds, muzzle flash, decals),
  heirlooms, the HUD drawn by the game's own UI code, and the Firing Range's loot, inventory and racks.
- **Collision:** the game's own BVH4 collision + static prop collision trees, not render triangles.
- **Next:** fog, water, zipline hands and view roll, then client/server.
