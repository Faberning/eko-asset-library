# eko-asset-library

Eko's owned, reusable, **licence-clean** image assets — the compounding library so we stop regenerating the same backgrounds, textures, and illustrative imagery each build.

**Source of truth = this repo.** Mirrored to the **Eko Media Docs** Drive/OneDrive folder for human browsing. Repo commit -> update the Drive mirror; never let the Drive copy become a second master.

> Icons do NOT live here — the owned SVG icon set lives in `eko-website-build/assets/icons/` so it travels with the build skill. This repo is for heavier raster imagery.

## What goes in (the scope fence)
- YES: Eko-generated/owned illustrative imagery, textures, backgrounds, mesh/gradient/noise assets we made.
- NEVER: client-owned photography, licensed stock, images with identifiable people, per-client brand/favicon marks, third-party trademarks, regulated-client imagery. Those stay in the client's project. When in doubt, out.

Full rule: `eko-website-build/references/icons-assets.md`.

## Structure

## Naming & manifest
- kebab-case, category-prefixed: `bg-mesh-navy.webp`, `texture-grain-fine.png`.
- Every file gets a manifest.json row: file, category, source (Flux/Grok/hand), licence (Eko-owned), date, origin build.

## Promotion (discipline, not ambient)
New qualifying assets are added during the build that makes them, with a manifest row. There is no background capture. Automating it = a promotion step in the Jabu/CI pipeline (future).
