# Owned Icon Set

The Eko owned SVG icon library. Grows as builds demand icons — check here **first** (sourcing waterfall in `../../references/icons-assets.md`).

## Rules
- **SVG only, monochrome, `currentColor`** — no baked-in colour, so one file recolors to any brand token. Optimised with SVGO.
- **One stroke system** — icons vendored from Lucide (default) or Phosphor must match on weight/cap/corner; bespoke icons are drawn to the same grid.
- **Every icon gets a `manifest.json` row** — `source` (library name + icon id, or "bespoke"), `licence`, `date`, `origin` build. Provenance is never guessed.
- **Licence-clean only** — Lucide (ISC), Phosphor/Heroicons/Tabler (MIT) are safe to vendor and relicense. Third-party *brand marks* do NOT belong here — they live in a separate `brand-marks/` folder from official kits only.

## Add an icon
1. Confirm it isn't already here.
2. Pull from the base family (or draw bespoke in the same system) → set to `currentColor` → SVGO.
3. Save as `icon-<name>.svg`, add its `manifest.json` row.

## Files
- `manifest.json` — provenance ledger for every icon in this folder.
- `icon-*.svg` — the set (grown per build).
