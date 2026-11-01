# SILLAGE AI Asset Production Plan

Source of truth for the visual production phase. This inventory was audited against the current `index.html`, `styles.css`, `modal.css`, `script.js`, `README_ASSETS.md`, and the filesystem on 1 November 2026.

No website source or existing asset was changed while preparing this plan.

## Executive inventory

The production plan contains **34 concrete image assets/slots** and one additional optional Journal detail convention (35 planned visual slots if that optional convention is counted):

- 2 hero/fallback WebP assets already present in `public/images/brand/`.
- 4 collection/product master images.
- 8 additional product gallery images: two per product.
- 9 unique ingredient images from the centralized product notes.
- 4 House editorial images.
- 6 concrete Journal/editorial image slots currently represented by code mappings: one featured cover and five story keys. Of these, `journal-story-05.webp` is mapped but not currently consumed by an article. The per-article detail pattern is an optional convention, not a concrete file today.
- 1 discovery consultation image slot.

The count above treats the 4 product masters, 8 product gallery frames, 9 ingredients, 4 House visuals, 6 Journal covers, and 1 discovery visual as distinct concrete slots, while excluding the two existing hero files from missing-production totals. The optional `articles/{article-slug}-01.webp` convention is documented separately and is not included in the 34 concrete slots.

### Current filesystem status

Existing image/video files:

- `public/images/brand/sillage-hero-after.webp` — exists; 2752×1536; used by the hero transition in `script.js`.
- `public/images/brand/sillage-hero-final.webp` — exists; 1280×720; referenced by the fallback rule in `modal.css` and documented as the converted final frame.
- `raw-assets/sillage-hero-after.webp` — exists; duplicate source/archive copy; not referenced by current runtime code.
- `raw-assets/*.jpg` — 10 supplied source images exist, but they are not in the root paths used by the legacy CSS/`ASSETS` mapping.
- `public/videos/sillage-hero.mp4` — exists; this is video, not counted as an image deliverable.

Missing production tree:

- `public/images/products/`
- `public/images/ingredients/`
- `public/images/editorial/`
- `public/images/editorial/articles/` (optional future detail imagery)

## Shared visual production specification

### Brand language

SILLAGE should read as dark editorial luxury: obsidian black, charcoal, smoked brown, muted champagne, warm amber, parchment ivory, and restrained mineral highlights. Images should feel architectural and quiet rather than glossy mass-market advertising.

### Lighting and camera

- Large, soft key light from upper-left or upper-front-left, with a controlled warm rim from the right when it helps separate glass from the background.
- Deep negative fill on the opposite side; preserve shape without crushing the bottle into black.
- Low-to-medium contrast with a rich black floor and a gently luminous central subject.
- Premium still-life camera aesthetic: 70–100 mm equivalent for products, macro lens language for materials, shallow depth of field only where it helps the subject.
- No visible studio equipment, no hands unless a brief explicitly requires them, no random props, no artificial text, no logos, no labels, no watermarks.
- Use the same bottle silhouette, cap geometry, glass thickness, shoulder proportions, atomizer, and metal finish across all four products. Product identity is expressed through atmosphere and palette, not by redesigning the bottle.

### Material and palette rules

- Heavy clear or lightly smoked glass with realistic refraction and a substantial base.
- Cap and hardware: brushed champagne metal or darkened satin metal; never bright chrome.
- Liquid tint may vary subtly by fragrance, but all bottles remain part of one family.
- Backgrounds: matte obsidian, charcoal, smoked umber, or desaturated stone. Avoid busy scenery.
- Atmospheric effects should be sparse: a veil of smoke, a pool of amber light, a dry mineral surface, or a single soft shadow. Avoid decorative gradients that compete with the object.
- Keep blacks detailed enough for responsive cropping and compression.

### Composition rules

- Do not generate typography, product names, labels, UI, or decorative lettering inside images. HTML/CSS supplies all text.
- Product masters reserve calm negative space around the bottle and keep the bottle inside a safe 70% central crop so `object-fit: cover` remains safe.
- For collection cards, place the bottle slightly right of center where possible, leaving the upper-left and lower text-safe zones calm.
- For hero/editorial frames, follow the slot-specific positioning below.
- Deliver a clean master plus a consistent crop strategy; do not bake an aggressive vignette into the file.

### Output rules

- Preferred format: WebP, quality 88–94, RGB unless transparency is specifically required.
- Transparency: **no** for all current background/image-slot assets. The website uses full-frame editorial backgrounds and CSS placeholders, not cutout compositing.
- Keep the original AI master outside the website tree; deliver only approved WebP derivatives into the exact paths below.
- Avoid embedded text and avoid EXIF-dependent orientation.
- Validate every delivered file under the direct `file://` path used by the site.

## Complete asset inventory

### A. Brand and Hero

| Asset / exact path | Section and code reference | Exists | Runtime reference | Specification and visual brief | Priority |
|---|---|---:|---:|---|---|
| `public/images/brand/sillage-hero-after.webp` | Hero final image; `FINAL_IMAGE_URL` in `script.js` | Yes — 2752×1536 | Yes | 16:9 recommended; existing 1.79:1 source is suitable for the full viewport. Permanent final scene: perfume bottle on the right, generous dark text-safe space on the left, soft amber/champagne atmosphere, no baked typography. WebP, opaque. | Existing / approved |
| `public/images/brand/sillage-hero-final.webp` | Hero fallback rule in `modal.css`; README conversion target | Yes — 1280×720 | Yes, CSS fallback | 16:9, 1920×1080 preferred for final delivery if this remains a distinct fallback. It should be the clean final video frame or a visually matching fallback, with the same right-side bottle and left-side negative space. WebP, opaque. | Existing / verify |
| `public/images/brand/sillage-logo.svg` | Listed in `README_ASSETS.md`, but current header/footer use text `SILLAGE` | No | No | Not an image slot in current runtime. Defer unless the brand wordmark is intentionally migrated to SVG in a later implementation phase. | Deferred |

The current hero video is `public/videos/sillage-hero.mp4`; it is not an image generation deliverable. The archive `raw-assets/sillage-hero-original.mp4.mp4` is not a website image slot.

### Legacy image references found in current CSS/HTML

These are literal references found in the source, separate from the active canonical production paths. They currently resolve relative to the project root under `file://`, but the matching supplied files are in `raw-assets/`, so they are path inconsistencies rather than approved delivery locations:

- `SILLAGE_perfume_bottle_commercia…_da254600.mp4` — legacy CSS background reference; it is a video-like filename used as an image background and no matching file exists in the project.
- `Perfume_bottle_surrounded_by_mist_69308868_2K.jpg` — legacy hero fallback/product reference; source exists only as `raw-assets/Perfume_bottle_surrounded_by_mist_69308868_2K.jpg`.
- `Oud_agarwood_resin_close_up_5db3ad9d_2K.jpg` — static `#notes` fallback and legacy ingredient reference; source exists only under `raw-assets/`.
- `Luxury_fragrance_bottles_on_pede…_1950c1bf_2K.jpg` — legacy House background reference; source exists only under `raw-assets/`.
- `Perfume_bottle_product_photograph_eb1673be_2K.jpg` — legacy product/quiz reference; source exists only under `raw-assets/`.
- `Dewdrops_on_dark_rose_petals_88a9df5c_2K.jpg`, `Bergamot_citrus_with_oil_droplets_90395180_2K.jpg`, and `Vanilla_pods_with_natural_oils_cc0a1cee_2K.jpg` — legacy Journal CSS references; source files exist only under `raw-assets/`.
- `Macro_photograph_of_perfume_atom…_78e22473_2K.jpg` and `Perfume_atomizer_spraying_fragra…_f328a27c_2K.jpg` — legacy product mappings; source files exist only under `raw-assets/` and contain literal Unicode ellipses in their filenames.

### B. Product Collection

The collection renderer uses `productImagePath(id)` in `script.js` and expects the following exact paths. All four are currently missing.

| Product | Exact path | Section / reuse | Ratio and output | Visual brief | Priority |
|---|---|---|---|---|---|
| NOIR ABSOLU | `public/images/products/product-01.webp` | Collection card, product detail main visual, related cards, discovery result | 4:5; 1600×2000 preferred, minimum 1200×1500; WebP, opaque | Master bottle portrait on a charcoal-to-obsidian ground, deep woody shadow, subtle amber rim, bottle slightly right of center, mysterious and sophisticated, crisp glass and restrained reflection. | Batch 01 / P1 |
| VELVET OUD | `public/images/products/product-02.webp` | Same shared product/detail/discovery slots | 4:5; 1600×2000; WebP, opaque | Same bottle family; richer umber atmosphere, warm low light, a soft veil of depth suggesting oud without literal forest props. Bottle remains legible and premium. | Batch 01 / P1 |
| AMBRE NOIR | `public/images/products/product-03.webp` | Same shared product/detail slots | 4:5; 1600×2000; WebP, opaque | Same bottle family; muted amber glow, smoked bronze accents, warm resinous mood, slightly more luminous than Noir Absolu but still dark and editorial. | Batch 01 / P1 |
| ÉCLAT BLANC | `public/images/products/product-04.webp` | Same shared product/detail/discovery slots | 4:5; 1600×2000; WebP, opaque | Same bottle family; pale stone/charcoal background, cool ivory light, clean glass highlight, restrained floral/fresh atmosphere, luminous without becoming white commercial beauty photography. | Batch 01 / P1 |

The older `ASSETS.products` mapping at the top of `script.js` points to root-level filenames such as `Perfume_bottle_product_photograph_eb1673be_2K.jpg`. Those files do not exist at the root; their source counterparts are under `raw-assets/`. The active production mapping uses the four `public/images/products/product-0N.webp` paths, which are currently absent. Do not place final files at the old root names.

### C. Product Detail Galleries

`productGalleryPaths(id)` derives these exact names from each product master. None currently exists.

| Product | Exact additional paths | Ratio / output | Visual brief and reuse |
|---|---|---|---|
| NOIR ABSOLU | `public/images/products/product-01-detail-01.webp`; `public/images/products/product-01-detail-02.webp` | 4:5; 1600×2000 each; WebP, opaque | Detail 01: shoulder, cap and glass/refraction close-up. Detail 02: bottle in a wider atmospheric still life with the same lighting. Reuse the master bottle and materials; do not invent a new bottle. |
| VELVET OUD | `public/images/products/product-02-detail-01.webp`; `public/images/products/product-02-detail-02.webp` | 4:5; 1600×2000 each; WebP, opaque | Macro glass/metal detail plus a warm oud atmosphere. Keep the exact master silhouette and cap. |
| AMBRE NOIR | `public/images/products/product-03-detail-01.webp`; `public/images/products/product-03-detail-02.webp` | 4:5; 1600×2000 each; WebP, opaque | Resinous amber reflection detail plus a composed bottle still life. Avoid literal amber chunks unless elegant and sparse. |
| ÉCLAT BLANC | `public/images/products/product-04-detail-01.webp`; `public/images/products/product-04-detail-02.webp` | 4:5; 1600×2000 each; WebP, opaque | Cool glass/highlight detail plus a clean luminous still life. Keep contrast and edges visible on the pale ground. |

The current product-detail template creates the `detail` path array but does not yet render gallery thumbnails or frames. These are therefore prepared production slots, not currently visible DOM image elements. They should be generated after the four master bottles are approved.

### D. Fragrance Ingredients

The centralized product data in `script.js` contains nine unique note names:

| Ingredient | Exact planned path | Products / runtime use | Exists | Ratio / output | Visual brief | Priority |
|---|---|---|---:|---|---|---|
| Bergamot | `public/images/ingredients/bergamot.webp` | Noir top; Éclat top; Scent Story; `ingredientPaths` | No | 1:1; 1600×1600; WebP | Cut bergamot with oil pores and a restrained citrus sheen on dark stone, architectural crop, no recipe styling. | Batch 03 / P1 |
| Rose | `public/images/ingredients/rose.webp` | Noir heart; Éclat heart; Scent Story; `ingredientPaths` | No | 1:1; 1600×1600; WebP | One dark rose or petal structure with dew and sculptural shadow; avoid romantic pink excess. | Batch 03 / P1 |
| Oud | `public/images/ingredients/oud.webp` | Noir base; Velvet base; Scent Story; `ingredientPaths`; initial `#notes` fallback uses raw Oud JPG | No at planned path; raw source exists | 1:1; 1600×1600; WebP | Agarwood/resin macro, dark brown grain, controlled warm highlight, tactile and mineral. Reuse as one shared image across Noir, Velvet, and Scent Story. | Batch 03 / P1 |
| Vanilla | `public/images/ingredients/vanilla.webp` | Éclat base; Scent Story; `ingredientPaths` | No | 1:1; 1600×1600; WebP | Pale vanilla pod and creamy texture against charcoal, quiet and refined rather than dessert-like. | Batch 03 / P1 |
| Saffron | No path is currently defined | Velvet top; Scent Story dynamically requests an unmapped ingredient placeholder | No mapped asset | 1:1; 1600×1600; WebP | Fine saffron threads, dry crimson-gold texture, minimal composition on obsidian. Add a canonical path before implementation consumes it. | Batch 03 / P1 |
| Iris | No path is currently defined | Velvet heart; dynamic Scent Story unmapped placeholder | No mapped asset | 1:1; 1600×1600; WebP | Cool violet/grey iris texture or root-inspired botanical detail, abstract and architectural, not a generic flower bouquet. | Batch 03 / P2 |
| Pink pepper | No path is currently defined | Ambre top; dynamic Scent Story unmapped placeholder | No mapped asset | 1:1; 1600×1600; WebP | Sparse pink peppercorns with dry warm light, restrained pink accent, dark ground. | Batch 03 / P2 |
| Amber | No path is currently defined | Ambre heart; dynamic Scent Story unmapped placeholder | No mapped asset | 1:1; 1600×1600; WebP | Translucent amber/resin glow, sculptural and mineral, no literal jewellery look. | Batch 03 / P1 |
| Benzoin | No path is currently defined | Ambre base; dynamic Scent Story unmapped placeholder | No mapped asset | 1:1; 1600×1600; WebP | Dark balsamic resin, warm brown-gold highlights, tactile macro with quiet negative space. | Batch 03 / P2 |

The four mapped ingredient filenames are a planned canonical system, but the corresponding files are not yet present. The five unmapped notes are real runtime note values and must not be omitted from the production plan. They need a path decision in a later implementation pass; this audit does not modify `script.js`.

### E. The Scent Story

The `#notes` section is replaced at runtime by `renderScentStory()`. It displays one selected product and three note-stage visuals. The same nine ingredient assets above are reused across all product selections; no separate image is needed per product-note combination.

| Slot | Exact path | Ratio / output | Placement |
|---|---|---|---|
| Selected product top note | Ingredient path for the product's top note | 1:1; 1600×1600 | Three-stage Scent Story grid, top-note card; leave text to HTML. |
| Selected product heart note | Ingredient path for the product's heart note | 1:1; 1600×1600 | Three-stage Scent Story grid, heart-note card. |
| Selected product base note | Ingredient path for the product's base note | 1:1; 1600×1600 | Three-stage Scent Story grid, base-note card. |

The initial static HTML contains `.notes-image.image-oud` with `Oud_agarwood_resin_close_up_5db3ad9d_2K.jpg`, but `renderScentStory()` replaces that markup on load. Treat the raw Oud photograph as an existing source/reuse candidate, not as a final canonical web asset.

### F. The House

`houseAssets` defines four exact runtime paths. All are missing.

| Exact path | Runtime slot | Ratio / output | Visual brief | Priority |
|---|---|---|---|---|
| `public/images/editorial/house-philosophy.webp` | House opening / “The art of being remembered” | 4:5; 1800×2250; WebP | Architectural fragrance still life: one bottle or abstract glass form emerging from shadow, quiet sense of philosophy and presence, right/central subject with calm copy space. | Batch 04 / P1 |
| `public/images/editorial/house-materials.webp` | “Our belief” / materials | 4:5; 1800×2250; WebP | Macro study of glass, brushed metal, stone, paper, and dark material surfaces; tactile, precise, no text. | Batch 04 / P1 |
| `public/images/editorial/house-atmosphere.webp` | Sillage signature / atmosphere | 4:5; 1800×2250; WebP | Abstract atmospheric composition of shadow, light, glass and a restrained amber trace; suggest memory without literal smoke overload. | Batch 04 / P1 |
| `public/images/editorial/house-signature.webp` | Closing manifesto visual | 16:7; 2400×1050; WebP | Wide cinematic brand still life with a low horizon, small bottle/trace positioned off-center, large negative space for the closing copy, deep obsidian palette. | Batch 04 / P1 |

### G. Find Your Scent

The discovery experience has these visual slots:

| Slot | Current implementation | Exact production path | Ratio / output | Brief | Status |
|---|---|---|---|---|---|
| Discovery consultation intro | `.discovery-visual` CSS placeholder; no `data-image-path` | No path is defined in current code | 4:3; 1600×1200; WebP, opaque | Private consultation atmosphere: dark table, glass, paper/card edge or abstract bottle shadow, understated and text-safe. | Missing path decision; Batch 06 / P2 |
| Discovery primary result | Reuses `productImagePath(primary.id)` | One of the four product masters | 4:5; 1600×2000 | Use the approved product master; no duplicate generation. | Reuse |
| Discovery alternatives | Reuses product-specific CSS visual classes and paths | One of the four product masters | 4:5; 1600×2000 | Reuse approved product masters. | Reuse |

The initial legacy quiz renderer also referenced `Perfume_bottle_product_photograph_eb1673be_2K.jpg`, but the active discovery renderer uses canonical product paths. Do not generate a separate quiz bottle set.

### H. The Journal

`journalAssets` defines six cover keys. Five are currently attached to the five article records; `story05` is mapped but not consumed by the current five article data.

| Exact path | Article / runtime use | Ratio / output | Visual brief | Priority |
|---|---|---|---|---|
| `public/images/editorial/journal-featured.webp` | Article 01, “The Art of Choosing a Signature Scent”; featured Journal card and detail | 16:9; 2400×1350; WebP | Editorial still life about choosing a signature: bottle silhouette, shadow, paper/stone, generous composition and no text. | Batch 05 / P1 |
| `public/images/editorial/journal-story-01.webp` | Article 02, “Understanding the Architecture of Fragrance” | 4:3; 1800×1350; WebP | Layered architectural composition showing progression or structure: glass, shadow, measured planes, restrained material language. | Batch 05 / P1 |
| `public/images/editorial/journal-story-02.webp` | Article 03, “The Beauty of Oud” | 4:3; 1800×1350; WebP | Oud/agarwood macro related to the shared ingredient asset but composed as a distinct editorial scene, not a duplicate crop. | Batch 05 / P1 |
| `public/images/editorial/journal-story-03.webp` | Article 04, “Beyond the First Impression” | 4:3; 1800×1350; WebP | A fragrance changing through time: opening light fading into a darker trace, abstract and atmospheric. | Batch 05 / P2 |
| `public/images/editorial/journal-story-04.webp` | Article 05, “The Language of Fragrance” | 4:3; 1800×1350; WebP | Abstract visual vocabulary of materials, contrast and air; refined, quiet, no literal typography. | Batch 05 / P2 |
| `public/images/editorial/journal-story-05.webp` | Defined in `journalAssets`, not attached to any current article | 4:3; 1800×1350; WebP | Hold as reserve for a sixth story or future replacement; do not produce until content is assigned. | Deferred |
| `public/images/editorial/articles/{article-slug}-01.webp` | Optional README pattern; not emitted by current Journal renderer | Per article; 4:3 or 16:9; WebP | Only create for an article that later receives an in-body visual. Use the article's own subject and avoid repeating its cover. | Deferred |

Journal cover images are reused between the Journal home and article detail routes. They should be composed to survive both the wide featured treatment and the detail cover crop.

### I. Newsletter and Footer

No image asset slots are used by the newsletter or footer in the current code. The wordmark is HTML text, the footer contains text links, and the newsletter is a form. No AI image production is required for this category.

## Existing asset reuse opportunities

The `raw-assets/` directory contains ten supplied JPG/WebP sources that can inform or, where quality/composition is approved, seed the production workflow:

| Existing source | Dimensions | Best reuse candidate | Constraint |
|---|---:|---|---|
| `raw-assets/Perfume_bottle_product_photograph_eb1673be_2K.jpg` | 2752×1536 | Noir Absolu/product-master reference; legacy `ASSETS.products.noir` | Current code references a root-level copy that does not exist. Review before using as the canonical Noir image. |
| `raw-assets/Perfume_bottle_surrounded_by_mist_69308868_2K.jpg` | 2752×1536 | Velvet Oud/product-master reference; legacy `ASSETS.products.velvet`; hero fallback legacy reference | Review crop and product continuity; do not automatically reuse for both hero and product. |
| `raw-assets/Macro_photograph_of_perfume_atom…_78e22473_2K.jpg` | 2752×1536 | Ambre Noir/product-master reference; legacy `ASSETS.products.ambre` | Filename contains a literal Unicode ellipsis; preserve the archive name, but deliver the approved asset at canonical `product-03.webp`. |
| `raw-assets/Perfume_atomizer_spraying_fragra…_f328a27c_2K.jpg` | 2752×1536 | Éclat Blanc/product-master reference; legacy `ASSETS.products.eclat` | Filename contains a literal Unicode ellipsis; inspect whether the spraying composition matches the bottle master. |
| `raw-assets/Oud_agarwood_resin_close_up_5db3ad9d_2K.jpg` | 1792×2400 | Oud ingredient and initial Scent Story fallback | Strongest direct reuse candidate; crop/re-export to `public/images/ingredients/oud.webp` if approved. |
| `raw-assets/Bergamot_citrus_with_oil_droplets_90395180_2K.jpg` | 1792×2400 | Bergamot ingredient reference | Crop/re-export to canonical square WebP; preserve dark editorial grading. |
| `raw-assets/Dewdrops_on_dark_rose_petals_88a9df5c_2K.jpg` | 1792×2400 | Rose ingredient / legacy Journal image reference | Can inform Rose, but Journal should receive a distinct editorial cover if the same composition would repeat. |
| `raw-assets/Vanilla_pods_with_natural_oils_cc0a1cee_2K.jpg` | 1792×2400 | Vanilla ingredient / legacy Journal image reference | Crop/re-export to canonical square WebP; avoid duplicate Journal usage unless intentionally approved. |
| `raw-assets/Luxury_fragrance_bottles_on_pede…_1950c1bf_2K.jpg` | 2752×1536 | House materials/atmosphere reference; legacy `.house-image` | Filename contains a literal Unicode ellipsis; current CSS references a root-level file that is absent. |
| `raw-assets/sillage-hero-after.webp` | 2752×1536 | Hero archive duplicate | Reuse only as source comparison; runtime should continue using `public/images/brand/sillage-hero-after.webp`. |

The source files are not currently loaded from `raw-assets/` by the browser. Production should approve visual continuity first, then place final derivatives at the canonical public paths rather than modifying source code as part of this image phase.

## Production batches

### Batch 01 — Master bottle and four product images

1. Approve one shared bottle design language: bottle silhouette, cap, atomizer, glass, base, and metal finish.
2. Produce `product-01.webp` through `product-04.webp` at 4:5, 1600×2000 or larger.
3. Validate collection card crop, product detail crop, related cards, and discovery result reuse.

### Batch 02 — Additional product gallery images

Produce the eight `product-0N-detail-01.webp` and `product-0N-detail-02.webp` files only after the master images are approved. Keep lighting, camera height, and bottle geometry consistent.

### Batch 03 — Unique fragrance ingredients

Produce the nine unique note visuals: Bergamot, Rose, Oud, Vanilla, Saffron, Iris, Pink pepper, Amber, and Benzoin. Start with the four path-backed notes and resolve canonical paths for the five unmapped notes before implementation consumes them.

### Batch 04 — The House editorial imagery

Produce the four House files, with the wide signature image last because it needs to coordinate with the closing copy and responsive crop.

### Batch 05 — Journal imagery

Produce the five active covers. Defer `journal-story-05.webp` until a sixth story exists. Defer article-detail imagery until an article actually needs an in-body visual.

### Batch 06 — Remaining visual assets

Resolve the discovery consultation image path and asset. No newsletter/footer images are required. Any future logo migration is a separate brand-system task, not part of this batch.

## Priority order

1. Hero verification and preservation — existing, no generation required.
2. Four product masters — highest repeated visual impact across collection, detail, related products, and discovery.
3. Oud, Bergamot, Rose, Vanilla, Amber — repeated or high-visibility note materials.
4. Product detail galleries — important for product depth after the masters are approved.
5. House opening/materials/atmosphere/signature — brand credibility and long-form editorial impact.
6. Journal featured cover and four active story covers.
7. Saffron, Iris, Pink pepper, Benzoin — required for complete note coverage but less frequently surfaced than the first group.
8. Discovery consultation visual and deferred Journal assets.

## Missing asset report

There are **32 concrete missing production slots**: 12 product master/gallery files, 4 path-backed ingredient files, 4 House files, 6 Journal cover files, 5 currently unmapped ingredient visuals, and 1 discovery consultation visual. Of those, 26 have exact canonical filenames already defined in source; 6 require a path decision before implementation can load them.

### Missing but actively referenced or rendered

- `public/images/products/product-01.webp` through `product-04.webp`.
- `public/images/ingredients/bergamot.webp`, `rose.webp`, `oud.webp`, `vanilla.webp`.
- `public/images/editorial/house-philosophy.webp`, `house-materials.webp`, `house-atmosphere.webp`, `house-signature.webp`.
- `public/images/editorial/journal-featured.webp`, `journal-story-01.webp`, `journal-story-02.webp`, `journal-story-03.webp`, `journal-story-04.webp`.
- Five note visuals have runtime note values but no current path: Saffron, Iris, Pink pepper, Amber, Benzoin.
- The discovery intro visual is a CSS placeholder with no defined asset path.

### Missing but prepared/deferred

- Eight product detail gallery files derived by `productGalleryPaths(id)`.
- `public/images/editorial/journal-story-05.webp`, mapped but unused.
- Optional `public/images/editorial/articles/{article-slug}-01.webp` files.
- `public/images/brand/sillage-logo.svg`, documented but not referenced by the current DOM.

### Path inconsistencies

1. Active canonical product paths point to `public/images/products/`, but that directory is absent.
2. Active ingredient, House, and Journal paths point to `public/images/ingredients/` and `public/images/editorial/`, but those directories are absent.
3. The legacy `ASSETS.products` mapping points to root-level JPG names; the matching supplied source files are under `raw-assets/`, so those legacy URLs do not resolve under direct `file://` execution.
4. Several CSS backgrounds also use root-level JPG names, while the files live under `raw-assets/`.
5. Two hero final-frame files exist: `public/images/brand/sillage-hero-after.webp` is the active transition image; `public/images/brand/sillage-hero-final.webp` is the documented/fallback frame. Keep both roles explicit.
6. The two filenames containing a Unicode ellipsis in `raw-assets/` are exact archive names. Do not use shortened ASCII guesses when auditing or migrating them.
7. `journal-story-05.webp` is in the centralized map but has no current article consumer.
8. Product notes contain five unmapped ingredients. The current `ingredientPaths` map is incomplete relative to the centralized product data.

## Handoff checklist

- [ ] Approve one bottle family before generating four product masters.
- [ ] Keep all generated images free of typography, logos, labels, and watermarks.
- [ ] Deliver final files at the exact canonical paths in this document.
- [ ] Verify 4:5 product crops at collection-card and detail widths.
- [ ] Verify square ingredient crops inside all three Scent Story stages.
- [ ] Test every WebP under `file:///C:/Users/DELL/Desktop/SILLAGE/index.html` after copying assets.
- [ ] Confirm missing-image CSS placeholders remain graceful until each batch lands.
- [ ] Do not modify `index.html`, `styles.css`, `modal.css`, or `script.js` during image generation unless a separate implementation task explicitly maps the five currently unmapped ingredients or activates deferred galleries.
