# Icons, Favicons & the Asset Library

The mechanical asset layer — how Eko sources icons, generates favicons, handles third-party marks, and grows a **compounding owned library** instead of regenerating the same assets each build. Assets are decorative, so the DOM-text and GEO rules don't bite here; the fences that **do** apply are IP, consent, and licensing, inherited from `geo-honesty-spine.md`. The governing principle: **own it once, reuse it forever — but only what is actually ours to reuse.**

## Icon system — owned SVG set, seeded then grown

**Format law (non-negotiable):** production icons are **SVG, monochrome, drawn with `currentColor`** so one file recolors to any client's brand token, stays sharp at any DPI, and weighs a few KB. Optimised through SVGO. **No raster icons in production, ever** — an AI-generated neon-glow raster can't restyle for a non-yellow brand, softens on retina, and adds weight the perf/GEO budget won't spend. Raster icon sheets are at most a *reference for what to draw*, never files that enter the system.

**Sourcing waterfall (in order — stop at the first that satisfies):**
1. **The owned library** (`assets/icons/`) — check first, always. The point of the library is that this step usually ends it.
2. **The MIT/ISC base family** — Lucide (default) or Phosphor. Vendor in the *specific* icon needed, set it to `currentColor`, optimise, and **save it into the owned library** with a manifest entry. This is the "seed from an open base" path — it gives instant stroke consistency.
3. **Bespoke SVG** — draw it in the same stroke system (weight, cap, corner radius, grid) when the base family lacks it. Save to the library.

**One family per site.** Never mix stroke systems (the tell of a templated site). Lucide (ISC) and Phosphor/Heroicons/Tabler (MIT) are licence-clean to vendor and relicense into the owned set; record the source + licence in the manifest so provenance is never lost.

## Third-party brand marks — separate, official only

Vendor logos (OpenAI, Gemini, Claude, Copilot, Meta, Google, Bing, LinkedIn, YouTube, Instagram, X, Zoom, Teams, etc.) live in a **separate `brand-marks/` folder, sourced only from each vendor's official brand kit** (the real SVG + its usage terms). **Never an AI redraw or approximation** — that's a trademark problem an AI redraw doesn't launder, and the output is visibly wrong (garbled marks, mixed weights). Two honesty fences on top:
- A "platforms we optimise for" / "trusted by" / "as featured in" row must **not imply a partnership, endorsement, or client relationship that isn't real** — marks are used descriptively only, and client/press logos still require consent (`geo-honesty-spine.md`).
- Respect each kit's usage terms (clear-space, colour, don't-modify rules).

## Favicons — deterministic pipeline (per-client, not library)

From **one source mark** (SVG or ≥512px PNG), generate the full modern set in-container (sharp / Pillow / ImageMagick — **free, no cost gate**):
- `favicon.svg` · `favicon.ico` (multi-res 16/32/48) · `apple-touch-icon.png` (180) · maskable `192`/`512` · `site.webmanifest` · `theme-color` · and the exact `<head>` block.

Favicons are **client-specific** — they live in that client's project, **not** the shared library. Favicon presence is a small legitimacy signal in search/GBP, so it's part of the launch set, not an afterthought.

## AI raster (Grok / Flux) = imagery, not icons

AI-generated raster is **imagery only** — hero/card backgrounds, textures, illustrative stock. It is **cost-gated** (Bok's rule — pause for OK before generating). It is **never** an icon (icons are SVG) and **never** passed off as a client's real premises, people, team, or proof (honesty). Cull generation artefacts (garbled text, extra fingers, duplicate near-variants) before anything is kept.

## The Asset Library — scope, homes, promotion

**Scope — the fence (this is the whole reason the rule isn't "all images"):** only **Eko-owned, reusable, licence-clean** assets are promoted:
- ✅ bespoke SVG icons we drew · vendored MIT/ISC base icons · AI-generated *illustrative* imagery / textures / backgrounds Eko generated and owns.
- ❌ **never:** client-owned photography · licensed stock · images containing identifiable people · per-client brand or favicon marks · third-party trademarks · regulated-client imagery.

Anything in the ❌ list stays in that client's project only. Reusing it elsewhere is the exact IP/consent/honesty failure the system fences everywhere else — one client's real premises photo must never surface on another's page. When in doubt, it does **not** go in the library.

**Homes (both, mirrored):**
- **Owned SVG icon set → `eko-website-build/assets/icons/`** — versioned with the skill, so it travels with every build. This is the fast, always-present layer.
- **Heavier raster/image library → the `eko-asset-library` git repo, mirrored to the Eko Media Docs Drive/OneDrive folder.** The **repo is source of truth**; the Drive folder is the human-browsable mirror. Keep them in sync (repo commit → Drive mirror), never let the Drive copy diverge as a second master.

**Promotion is a discipline, not ambient capture.** There is no background process that grabs every image from every conversation. During a build, when a reusable Eko-owned asset is created, **save it to the library then, with a manifest entry** (name, category, source, licence, date, originating build). If you want this closer to automatic, that's a **promotion step in the Jabu/CI pipeline** — a future build-out, not something the skill does on its own. Until then: the build follows the rule; the rule is the enforcement.

**Naming & metadata:** kebab-case, category-prefixed (`icon-search.svg`, `bg-mesh-navy.webp`). Every asset has a `manifest.json` row recording `source` + `licence` + `origin` + `date` so nothing's provenance is ever guessed later.

## De-dupe / consistency (check before you generate)

Before drawing or generating anything, **search the library first** — this is what makes it compound instead of bloat. One stroke family per site; cull near-duplicates on entry; no garbled AI text in any kept asset. A library's entire value is coherence, so the bar to add is "consistent and owned," not "exists."
