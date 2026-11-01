# SILLAGE asset guide

The site currently uses the supplied local assets directly from the project root. For a future cleanup, move them into `public/images/brand`, `public/images/products`, `public/images/ingredients`, and `public/images/editorial`, then update the centralized `ASSETS` object in `script.js`.

| Current file | Intended use | Recommended ratio |
| --- | --- | --- |
| `SILLAGE_perfume_bottle_commercia…_da254600.mp4` | Hero video; autoplay, muted, plays once | 16:9 or 16:10 |
| `Perfume_bottle_product_photograph_eb1673be_2K.jpg` | Noir Absolu product / quiz result | 4:5 |
| `Perfume_bottle_surrounded_by_mist_69308868_2K.jpg` | Velvet Oud product | 4:5 |
| `Macro_photograph_of_perfume_atom…_78e22473_2K.jpg` | Ambre Noir product | 4:5 |
| `Perfume_atomizer_spraying_fragra…_f328a27c_2K.jpg` | Éclat Blanc product | 4:5 |
| `Oud_agarwood_resin_close_up_5db3ad9d_2K.jpg` | Fragrance architecture / oud story | 4:5 |
| `Dewdrops_on_dark_rose_petals_88a9df5c_2K.jpg` | Journal story 01 | 4:3 |
| `Bergamot_citrus_with_oil_droplets_90395180_2K.jpg` | Journal story 02 | 4:3 |
| `Vanilla_pods_with_natural_oils_cc0a1cee_2K.jpg` | Journal story 03 | 4:3 |
| `Luxury_fragrance_bottles_on_pede…_1950c1bf_2K.jpg` | The House feature | 16:9 |

If any file is missing, the surrounding dark editorial block remains intact and no broken image icon is rendered. No backend, payment gateway, or email storage is connected; cart persistence is browser-local only.

## Canonical future asset filenames

These are the intended production paths from the brief. They are not required for the current root-level demo, but should be used when the final asset set is supplied:

| Path | Used by | Ratio |
| --- | --- | --- |
| `/images/brand/sillage-logo.svg` | Header and footer wordmark | Vector |
| `/images/brand/sillage-hero-final.webp` | Exact final-frame fallback | 16:9 |
| `./public/images/products/product-01.webp` through `./public/images/products/product-04.webp` | Product collection and detail views; dark CSS placeholders are used until these files are supplied | 4:5 |
| `./public/images/products/product-01-detail-01.webp` and `product-01-detail-02.webp` (same pattern for 02–04) | Optional future product detail gallery frames; placeholders remain graceful when absent | 4:5 |
| `./public/images/ingredients/bergamot.webp` | Top-note editorial imagery | 1:1 |
| `./public/images/ingredients/rose.webp` | Heart-note editorial imagery | 1:1 |
| `./public/images/ingredients/oud.webp` | Base-note/editorial imagery | 1:1 |
| `./public/images/ingredients/vanilla.webp` | Base-note/editorial imagery | 1:1 |
| `./public/images/editorial/house-philosophy.webp` | The House opening philosophy visual | 4:5 |
| `./public/images/editorial/house-materials.webp` | The House belief / materials visual | 4:5 |
| `./public/images/editorial/house-atmosphere.webp` | The Sillage signature atmosphere visual | 4:5 |
| `./public/images/editorial/house-signature.webp` | The House closing manifesto visual | 16:7 |
| `./public/images/editorial/journal-featured.webp` | Featured Journal story cover | 16:9 |
| `./public/images/editorial/journal-story-01.webp` through `journal-story-05.webp` | Journal article covers and detail views | 4:3 or 16:9 |
| `./public/images/editorial/articles/{article-slug}-01.webp` | Optional future article-specific detail imagery | Editorial |
| `/images/editorial/story-01.webp` through `/images/editorial/story-03.webp` | Journal cards | 4:3 |
| `/videos/sillage-hero.mp4` | Single hero video | 16:9 |

Update only the `ASSETS` object in `script.js` when migrating from the current root-level filenames to these canonical paths.

## Journal editorial photography

The Journal uses these local WebP covers through the centralized `journalAssets` map in `script.js`. The same cover is reused on the Journal home card and the matching article detail route. Missing images preserve the existing dark editorial placeholder.

| Article | Asset path | Assignment |
| --- | --- | --- |
| 01 — The Art of Choosing a Signature Scent | `./public/images/editorial/journal-featured.webp` | Featured Journal story and article detail cover |
| 02 — Understanding the Architecture of Fragrance | `./public/images/editorial/journal-story-01.webp` | Story card and article detail cover |
| 03 — The Beauty of Oud | `./public/images/editorial/journal-story-02.webp` | Story card and article detail cover |
| 04 — Beyond the First Impression | `./public/images/editorial/journal-story-03.webp` | Story card and article detail cover |
| 05 — The Language of Fragrance | `./public/images/editorial/journal-story-04.webp` | Story card and article detail cover |

The image slots preserve the existing editorial layout; object positioning is tuned per cover and all cover typography remains HTML/CSS.

## House editorial photography

The House visuals use the centralized `houseAssets` map in `script.js` and local paths under `public/images/editorial` so they work in the Windows `file://` workflow. All four approved files are present and are loaded lazily inside their existing visual slots; missing files retain the dark editorial placeholder.

| Visual | Path | Website assignment | Composition |
| --- | --- | --- | --- |
| Philosophy | `./public/images/editorial/house-philosophy.webp` | House opening philosophy visual | Existing portrait slot; centered crop with slight upper emphasis |
| Materials | `./public/images/editorial/house-materials.webp` | House belief / materials visual | Existing portrait slot; centered crop |
| Atmosphere | `./public/images/editorial/house-atmosphere.webp` | Sillage signature atmosphere visual | Existing portrait slot; centered crop with slight upper emphasis |
| Signature | `./public/images/editorial/house-signature.webp` | Closing manifesto visual | 16:7 composition, centered crop |

## Discovery consultation photography

The Find Your Scent introduction uses one local WebP visual through the centralized `ASSETS.editorial.discovery` mapping in `script.js`. It loads inside the existing discovery visual slot and falls back to the dark editorial placeholder if unavailable.

| Asset | Path | Website assignment | Recommended format |
| --- | --- | --- | --- |
| Discovery consultation | `./public/images/editorial/discovery-consultation.webp` | Find Your Scent discovery introduction visual | WebP, 4:3, 1600x1200 |

The image is used without embedded text; the consultation caption, quiz copy, and controls remain HTML/CSS.

## Ingredient photography

These nine local WebP assets are the canonical ingredient visuals used by The Scent Story and product-detail scent architecture. Files are stored under `public/images/ingredients` for the direct `file://` development environment. Each asset is intended to remain square (1:1); the UI preserves the image crop and leaves the existing editorial background visible if a file is unavailable.

| Note display name | Central mapping | Intended use |
| --- | --- | --- |
| Bergamot | `./public/images/ingredients/bergamot.webp` | Noir Absolu top note; Éclat Blanc top note |
| Rose | `./public/images/ingredients/rose.webp` | Noir Absolu heart note; Éclat Blanc heart note |
| Oud | `./public/images/ingredients/oud.webp` | Noir Absolu base note; Velvet Oud base note |
| Vanilla | `./public/images/ingredients/vanilla.webp` | Éclat Blanc base note |
| Saffron | `./public/images/ingredients/saffron.webp` | Velvet Oud top note |
| Iris | `./public/images/ingredients/iris.webp` | Velvet Oud heart note |
| Pink pepper | `./public/images/ingredients/pink-pepper.webp` | Ambre Noir top note |
| Amber | `./public/images/ingredients/amber.webp` | Ambre Noir heart note |
| Benzoin | `./public/images/ingredients/benzoin.webp` | Ambre Noir base note |

## Product gallery detail frames

The product detail gallery reads these centralized optional assets. Each is intended to be WebP, 4:5, 1600x2000. Missing files are hidden at runtime without replacing the master image.

| Product | Detail 01 | Detail 02 | Intended visual purpose |
| --- | --- | --- | --- |
| NOIR ABSOLU | `product-01-detail-01.webp` | `product-01-detail-02.webp` | Shoulder/cap/glass close-up; wider atmospheric still life |
| VELVET OUD | `product-02-detail-01.webp` | `product-02-detail-02.webp` | Macro glass/metal detail; warm oud atmosphere |
| AMBRE NOIR | `product-03-detail-01.webp` | `product-03-detail-02.webp` | Resinous amber reflection detail; composed bottle still life |
| ÉCLAT BLANC | `product-04-detail-01.webp` | `product-04-detail-02.webp` | Cool glass/highlight detail; clean luminous still life |

## Hero media compatibility audit

## Shopping experience notes

- The shopping bag uses the centralized `products` data and persists only cart line items (`id`, `size`, and `qty`) in the browser's `localStorage` key `sillage-cart`.
- Checkout is a frontend-only demonstration. It calculates subtotal, complimentary demo shipping, and total locally; it does not process payments, transmit, or store customer contact details.
- Newsletter submission is also a frontend-only demonstration and does not send or store email addresses.

- Original source: `raw-assets/sillage-hero-original.mp4.mp4`.
- Target converted video: `public/videos/sillage-hero.mp4`.
- Target final frame: `public/images/brand/sillage-hero-final.webp`.
- Conversion status: complete using FFmpeg 9.0.2.
- Converted video: H.264/AVC High profile, `yuv420p`, 1280×720, 24 fps, 4.000 seconds, no audio stream, MP4 container with fast-start metadata.
- Final frame: extracted from the converted video at `public/images/brand/sillage-hero-final.webp`, 1280×720 WebP, 64,092 bytes.

Recommended inspection:

```powershell
ffprobe -v error -show_format -show_streams -of json "raw-assets/sillage-hero-original.mp4.mp4"
```

Recommended conversion:

```powershell
New-Item -ItemType Directory -Force public/videos, public/images/brand
ffmpeg -i "raw-assets/sillage-hero-original.mp4.mp4" -map 0:v:0 -an -c:v libx264 -profile:v high -pix_fmt yuv420p -crf 18 -preset slow -movflags +faststart public/videos/sillage-hero.mp4
ffmpeg -sseof -0.05 -i public/videos/sillage-hero.mp4 -frames:v 1 -c:v libwebp -quality 95 public/images/brand/sillage-hero-final.webp
```
