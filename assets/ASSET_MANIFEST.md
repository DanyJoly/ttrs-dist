# Asset Manifest

All runtime assets live under `public/assets` and are copied to `dist/assets` by `npm run build`.

## Status

The current runtime neon glass theme lives under `theme/neon-glass/`. Backgrounds are generated PNG exports from the local source image at `src-assets/backgrounds/kremlin-sunset.png`; the remaining theme images are local SVG files. Background music lives under `music/` and is copied from `src-assets/music/`. The game treats the theme images as required startup assets: if any required image fails to load, the app shows a visible loading error and blocks gameplay.

The earlier flat SVG block samples remain reference assets only and are not runtime fallbacks. Optional PNG replacement exports may still be added for cell sprites or icons after iPhone/PWA validation if SVG rendering quality or icon install support requires them.

## Required Runtime Icons

These paths are referenced by `manifest.json` and `index.html`.

| Path | Format | Dimensions | Purpose | Status |
|---|---:|---:|---|---|
| `icons/app-icon.svg` | SVG | 512 x 512 viewBox | PWA app icon, any purpose | Runtime themed |
| `icons/app-icon-maskable.svg` | SVG | 512 x 512 viewBox | PWA maskable app icon | Runtime themed |
| `icons/apple-touch-icon.svg` | SVG | 180 x 180 viewBox | iPhone home-screen touch icon | Runtime themed |

Optional PNG replacement exports may be added after iPhone/PWA validation:

| Path | Format | Dimensions | Purpose | Status |
|---|---:|---:|---|---|
| `icons/app-icon-192.png` | PNG | 192 x 192 | Manifest replacement icon | Planned if needed |
| `icons/app-icon-512.png` | PNG | 512 x 512 | Manifest replacement icon | Planned if needed |
| `icons/app-icon-maskable-192.png` | PNG | 192 x 192 | Maskable replacement icon | Planned if needed |
| `icons/app-icon-maskable-512.png` | PNG | 512 x 512 | Maskable replacement icon | Planned if needed |
| `icons/apple-touch-icon.png` | PNG | 180 x 180 | iOS touch icon replacement | Planned if needed |

## Neon Glass Theme Runtime Assets

Runtime path:

```text
theme/neon-glass/
```

Background export tooling:

- Source: `src-assets/backgrounds/kremlin-sunset.png`
- Command: `npm run assets:backgrounds` using the local ImageMagick `convert` CLI
- Crop guide: `src-assets/backgrounds/kremlin-sunset-crop-guide.png`

| Path | Format | Dimensions | Purpose | Status |
|---|---:|---:|---|---|
| `theme/neon-glass/backgrounds/portrait-stage.png` | PNG | 860 x 1864 px | Primary iPhone portrait Russian-inspired background | Generated runtime asset |
| `theme/neon-glass/backgrounds/desktop-stage.png` | PNG | 2880 x 1800 px | Desktop background / letterbox treatment | Generated runtime asset |
| `theme/neon-glass/blocks/neon-cells.svg` | SVG | 7 x 1 sprite sheet, 64 x 64 per cell | Neon glass tetromino cell sprites | Runtime themed asset |
| `theme/neon-glass/ui/hud-panel.svg` | SVG | 320 x 160 viewBox | HUD backing reference | Runtime themed asset |
| `theme/neon-glass/ui/preview-slot.svg` | SVG | 128 x 128 viewBox | Next-piece slot frame | Runtime themed asset |
| `theme/neon-glass/ui/table-row.svg` | SVG | 480 x 56 viewBox | High-score table row treatment | Runtime themed asset |
| `theme/neon-glass/effects/line-clear-strip.svg` | SVG | 640 x 64 viewBox | Line-clear neon sweep | Runtime themed asset |
| `theme/neon-glass/effects/tetris-burst.svg` | SVG | 320 x 320 viewBox | Four-line clear effect | Runtime themed asset |

Recommended PNG exports, if validation requires raster runtime art:

| Path | Format | Dimensions | Purpose | Status |
|---|---:|---:|---|---|
| `theme/neon-glass/blocks/neon-cells.png` | PNG | 7 x 1 sprite sheet, 64 x 64 per cell | Neon glass cell sprites | Optional follow-up |

## Background Music Runtime Assets

Runtime path:

```text
music/
```

The playlist order is owned by `src/audio/audio-engine.ts`. It starts with
`balalaika-dance-normal.mp3`, advances through the remaining tracks in order,
and repeats from the first track after the last track.

| Path | Format | Purpose | Status |
|---|---:|---|---|
| `music/balalaika-dance-normal.mp3` | MP3 | First background-music playlist track | Runtime music asset |
| `music/balalaika-dance-speed.mp3` | MP3 | Background-music playlist track | Runtime music asset |
| `music/balkan-chip-normal.mp3` | MP3 | Background-music playlist track | Runtime music asset |
| `music/balkan-chip-speed.mp3` | MP3 | Background-music playlist track | Runtime music asset |
| `music/pocket-caravan-1.mp3` | MP3 | Background-music playlist track | Runtime music asset |
| `music/pocket-caravan-2.mp3` | MP3 | Background-music playlist track | Runtime music asset |

## Existing Reference Assets

These files exist today and may remain as proof/reference assets. They do not satisfy the final concept-art target by themselves and are not loaded as runtime fallbacks.

| Path | Format | Dimensions | Purpose | Status |
|---|---:|---:|---|---|
| `blocks/i-block.svg` | SVG | 32 x 32 viewBox | I block reference sample | Legacy reference |
| `blocks/o-block.svg` | SVG | 32 x 32 viewBox | O block reference sample | Legacy reference |
| `blocks/t-block.svg` | SVG | 32 x 32 viewBox | T block reference sample | Legacy reference |
| `blocks/s-block.svg` | SVG | 32 x 32 viewBox | S block reference sample | Legacy reference |
| `blocks/z-block.svg` | SVG | 32 x 32 viewBox | Z block reference sample | Legacy reference |
| `blocks/j-block.svg` | SVG | 32 x 32 viewBox | J block reference sample | Legacy reference |
| `blocks/l-block.svg` | SVG | 32 x 32 viewBox | L block reference sample | Legacy reference |
| `asset-preview.html` | HTML | Responsive | Human review proof sheet | Runtime themed |

## Explicit Non-Assets

- No hold-piece panel, hold icon, or hold preview.
- No iPhone movement-button art; controls remain gestures.
- No baked HUD/menu/high-score text images.
- No separate asset for every tetromino shape or rotation.
- No remote images, CDN fonts, or network-loaded art.
- No modern political symbols, flags, slogans, or readable signage.

## Manifest References

`manifest.json` references:

- `assets/icons/app-icon.svg`
- `assets/icons/app-icon-maskable.svg`

`index.html` references:

- `assets/icons/apple-touch-icon.svg`
