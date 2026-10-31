# Arches Zoom

A webcam piece: walk toward the camera and the view zooms in through three layered arch images.
Rebuilt from an earlier p5.js sketch (2024), with the same behaviour.

Live: https://lukori.github.io/arches-zoom/

## How it works

- The webcam image is shrunk to 160×120, thresholded to black/white, and the black pixels are counted ("silhouette size").
- After the first 30 frames, the current count becomes the **baseline**. Stand still at your normal distance while the page loads.
- When the silhouette is bigger than the baseline (you came closer), zoom maps from 1× at the baseline to 10× at 1.5× the baseline, smoothed by 0.1 per frame.
- Layers: `3.webp` pink (top), `2.webp` purple (middle), `1.jpg` yellow corridor (bottom). Each layer zooms 35% faster than the one below. The top layer blurs quickly as you approach; the bottom layer sharpens.
- Reload the page to reset the baseline.

## Display

- Fills the browser window ("cover" scaling, so edges are cropped when the screen isn't 4:3).
- Click or press **F** for real fullscreen.

## Defaults

| Name | Value |
|---|---|
| `maxZoom` | 10 |
| `smoothingFactor` | 0.1 |
| baseline frames | 30 |
| zoom range | baseline → baseline × 1.5 |
| layer zoom step | ×1.35 |
