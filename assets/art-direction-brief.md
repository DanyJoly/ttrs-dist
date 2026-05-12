# Art Direction Brief

This file is a short asset-folder companion to the current visual source of
truth: `planning/product/VISUAL_SPEC.md`.

## Current Direction

- Neon glass tetrominoes using the locked traditional Tetris colors.
- Retro pixel-art rendering with crisp edges and deliberate pixel texture.
- Portrait-first composition.
- Russian-inspired night background: onion-dome architecture, snow, starry sky,
  lantern warmth, ornamental side borders, and deep blue/purple shadows.
- Arcade feel: bright blocks, dark stage, responsive visual feedback.

## Runtime Policy

- Required runtime assets live under `public/assets`.
- Backgrounds are generated PNG exports from
  `src-assets/backgrounds/kremlin-sunset.png`.
- Cells, UI surfaces, icons, and effects currently use local SVG assets.
- Missing required theme assets block gameplay with a visible loading error.
- Dynamic text remains live-rendered.
- No remote images, CDN fonts, or network-loaded art are allowed.

## Detailed References

- Visual requirements: `planning/product/VISUAL_SPEC.md`
- Runtime inventory: `public/assets/ASSET_MANIFEST.md`
- Background export notes: `src-assets/backgrounds/README.md`
