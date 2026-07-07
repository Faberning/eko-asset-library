# Page Skeletons (structural reference)

A reusable **section vocabulary** and six **page archetypes** — the structure and image-placement logic of a well-composed multi-page marketing site, abstracted from a reference comp set. This is layout scaffolding only: **no tokens, no palette, no copy, no numbers are encoded here.** Value system, colour, type and motion are chosen per client in Phase 1 (`design-rules.md`); the reference comps happened to be dark + single-accent, but that is one instance's choice, not the skeleton's — instantiate the mood the brand calls for.

**The one rule that governs how this file is used:** every content-bearing element that is a **number, a logo, a named person, a review score, a case result, or a NAP detail is a verified-or-omit slot** — marked `[SoT]` below. The scaffold ships those slots **empty**, gated on a source-of-truth record (`geo-honesty-spine.md`). An instantiation physically cannot render a stat card, logo wall, testimonial, case study, chart, or founder fact without a real record behind it. Structure is reusable; content is never carried over from a comp.

---

## Section vocabulary (the reusable blocks)

Named blocks the archetypes below assemble. Each notes its image role and any `[SoT]` slots.

- **Nav (sticky)** — logo + optional tagline slot · primary items with one dropdown · one persistent CTA. No `[SoT]`.
- **Split hero** — left: eyebrow → 2–3 line headline (accent lands on the last line only) → subhead → inline chips/checklist → dual CTA (primary + secondary, secondary often a play/▶ affordance). Right: the **signature**, bled off the right/top edge, with **floating metric cards** `[SoT]` overlaid on it. Signature is Phase-1's chosen vehicle (`design-rules.md`), not a mandatory render. This is where the orchestrated entrance lands and where the signature first appears to evolve down-page.
- **Portrait hero (person-led variant)** — same grid, but the right side is a cut-out portrait against the signature; left column is a person's positioning. All bio facts `[SoT]`.
- **Trust strip** — light or contrasting band of consented client/press logos `[SoT]`. Omit entirely if none are consented — never a placeholder logo wall.
- **Stat/impact row** — 3–4 metric cells, each a figure + label `[SoT]`. Omit any cell without a record; the row can render partially.
- **Emphasis band** — one full-bleed accent band mid-page carrying a short claim + 3–4 inline proof figures `[SoT]`. Visual punctuation; use once per page.
- **Feature/why grid** — 6-cell (2×3 or 3×2) icon + heading + one-line grid. Copy, not `[SoT]`, but claims still obey honesty fences.
- **Service grid** — N service cards, each icon + name + line + a short capability checklist. Structure only.
- **Checklist columns** — 2–3 columns each a titled list (e.g. Technical / Authority / Readiness). Structure only.
- **Process rail** — horizontal 3–4 step numbered rail with connectors. Structure only.
- **Case-study cards** — photographic card + a score/badge `[SoT]` + a 2–3 metric triplet `[SoT]` + link. **Whole block is `[SoT]`** — renders only with a real case record; the score badge and every metric trace to it.
- **Logo/engine row** — row of platform or partner marks. Only real, factual marks (e.g. AI engines a site genuinely targets); consented client/press logos are `[SoT]`.
- **Diagram block** — one system/flow diagram (e.g. ecosystem, entity graph). Illustrative-structural; if it contains figures they are `[SoT]`.
- **Timeline** — horizontal node sequence with dates + labels. Dates/claims `[SoT]`.
- **Chart block** — a plotted trend. **`[SoT]` and animation-gated** — an animated chart of unverified/"illustrative" numbers is banned (`geo-honesty-spine.md`); it renders only source-of-truth series, or it's omitted.
- **Testimonial cluster** — aggregate score `[SoT]` + attributed quotes `[SoT]`. Real + attributed + consented, or omitted. No composite/invented score.
- **Card wall** — article/insight cards (image + tag + read-time + title + author `[SoT]` + date). Author and date `[SoT]`.
- **Feature + sidebar** — one large featured item beside stacked secondary items and a report/newsletter rail.
- **Filter chips** — a topic/category filter row above a card wall.
- **Form block** — labelled fields + consent line + submit; paired with a get-in-touch column (channels + NAP `[SoT]`).
- **Location cards** — 2–3 office cards, each image + address `[SoT]` + map link. Addresses `[SoT]`; omit the block if remote-only.
- **FAQ block** — 1–2 column accordion. Native `<details>` or the defended accordion pattern per stack (`deploy-launch.md`). FAQPage schema attaches here.
- **Final-CTA band** — full-bleed atmospheric image, text + one CTA left-aligned. Image role: wide mood shot; no `[SoT]`.
- **Mega-footer** — logo + tagline · 4–5 link columns · socials · legal + business identifier `[SoT]` (e.g. NZBN as entity disambiguator).

---

## Image-placement logic (encode this, it's the reusable part)

1. **One signature, reused every page** — right/top-aligned, bled off the edge, metric cards floating over it. Consistency across pages is the point (`design-rules.md`: the signature evolves through the page, it does not restart as a new object per page).
2. **Card images are photographic + treated** — a consistent duotone/grade so a heterogeneous image set reads as one system; text overlays the lower third with a legibility scrim. Applies to case-study, location, and insight cards.
3. **The final-CTA band is the one wide atmospheric image** — full-bleed, text left, high contrast for the CTA.
4. **Icons over stock inside grids** — feature/service/process/checklist blocks use a single icon set, not photos, to keep density readable. (Icon set = `icons-assets.md`.)
5. **Every meaningful image carries alt text**; the signature is decorative-with-a-role but retrieval-critical meaning is never inside any raster (`geo-honesty-spine.md`, DOM-text supremacy).

---

## The six archetypes (block order per page type)

Same vocabulary, rearranged. `[SoT]` blocks render only with records.

**Home** — Nav · Split hero (+ metric cards `[SoT]`) · Trust strip `[SoT]` · Feature/why grid (6) · Emphasis band (+ figures `[SoT]`) · Service grid (6) · Location cards `[SoT]` · Final-CTA band · Footer.

**Services** — Nav · Split hero (+ metric cards `[SoT]`) · Service grid (6, with checklists) · Emphasis band · Checklist columns (Technical / Authority / Readiness) · Process rail (4) · Industry tiles (6) · Diagram block (ecosystem) + Stat/impact row `[SoT]` · FAQ (2-col) · Final-CTA band · Footer.

**Results** — Nav · Split hero (+ metric cards `[SoT]`) · Stat/impact row `[SoT]` · Case-study cards (3) `[SoT]` · Logo/engine row (real engines) + consented client logos `[SoT]` · Chart block `[SoT]` + growth table `[SoT]` · Testimonial cluster `[SoT]` · Final-CTA band · Footer. *(This page is almost entirely `[SoT]` — if the records don't exist yet, it degrades to a gap-demo, not a fabricated results page.)*

**About (person-led)** — Nav · Portrait hero (+ credential cards `[SoT]`) · Feature/why grid (4, "global perspective") · Timeline `[SoT]` · Feature grid (4, "mission") · Trust strip (press "featured in") `[SoT]` · Card wall (4, speaking/thought-leadership) · Final-CTA band · Footer. *(Most fabrication-dense archetype in the comp set — bio facts, tenure, follower counts, press logos, timeline dates are all `[SoT]`. No persona is invented.)*

**Insights (index)** — Nav · Split hero + search · Filter chips · Feature + sidebar (1 large + 2 stacked + report/newsletter rail) · Card wall (3×2) `[SoT]` on author/date · Load-more · Final-CTA band · Footer.

**Contact** — Nav · Split hero (+ metric cards `[SoT]`) · Form block + get-in-touch (NAP `[SoT]`) · Location cards `[SoT]` · Remote/global band (real meeting-platform marks) · FAQ + partnerships/careers panel · Final-CTA band · Footer.

---

## Motion & interaction hook (don't ship these flat)

The comps are static; a static instantiation FAILS the gate (`design-rules.md`, §14). Per archetype, the default kit lands as:
- **Entrance** — in the hero (headline settles, signature resolves, metric cards stagger in).
- **Reveals** — grids, rails, timelines, card walls reveal on scroll with directional intent.
- **Signature evolves** — across the hero → method/process → diagram beats down each page.
- **Interactive moment** (pick per vertical, build it — `capability-layer.md`): Services/Home → a live calculator or estimator for the vertical; Results → filterable/sortable case studies; Insights → the working search + topic filter; Contact → live form validation. Mortgage → repayment/deposit; trades → quote estimator; real estate → filterable listings.
- All fenced: reduced-motion fallback, LCP unblocked, real DOM text, keyboard paths, no meaning behind hover alone.

---

## Instantiation checklist

1. Load the **KB record** — the skeleton is inert without a source-of-truth spine.
2. Choose the **value system + tokens + signature** in Phase 1; do not inherit the comp's dark+accent look.
3. Drop only the **blocks the client has records for**; leave every `[SoT]` slot empty until a record fills it. A partial page beats a fabricated one.
4. Attach **schema** per block (Organization/LocalBusiness sitewide, FAQPage on FAQ, Service on service grids, Person on About, Article on insights, BreadcrumbList on deep pages).
5. Run **both gates** before done.
