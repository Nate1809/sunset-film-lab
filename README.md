# 夕景現像所 · SUNSET FILM LAB

A single-file, browser-based photo developer that recreates the **80s Japanese city-pop magazine-scan** aesthetic — warm faded film, halation bloom, grain, and authentic JPEG/print compression. Drop any photo and develop it.

> Everything runs locally in your browser. No uploads, no server, no dependencies.

## The look, deconstructed

That vintage flavor isn't one filter — it's a *stack* of effects layered in the order a real photo would acquire them (lens → film → scan → print → compression):

1. **Warm tungsten white-balance** — the amber/orange cast of old film + indoor light
2. **Faded film** — lifted blacks and low contrast (the milky, no-true-black look)
3. **Split tone** — golden highlights, teal shadows
4. **Halation** — warm bloom bleeding off the bright spots
5. **Grain** — fine film/scan luminance noise
6. **Chroma drift** — subtle red/cyan lens fringing toward the edges
7. **Compression** — the real tell: the image is *actually re-encoded* to a low-quality JPEG mid-pipeline, producing genuine 8×8 blocking and chroma subsampling, plus an optional CMYK halftone print screen

## Features

- 📱 **Mobile-first, app-style UI** — the image stays pinned in view while you edit (iOS Photos / Instagram style)
- 🎞️ **Filters carousel** with live per-photo thumbnails: `TATSURO '82`, `FOR YOU`, `RIDE ON TIME`, `SPARKLE`, `PLASTIC LOVE`, `MIDNIGHT`
- 🎛️ **Adjust** tab — 12 tools (warmth, tint, saturation, fade, split tone, halation, chroma drift, pixel chroma, grain, compression, print screen, vignette) with a single focused slider
- 🔀 **Press & hold** the photo to compare before/after
- 🖼️ Drag & drop, tap to browse, or paste from clipboard
- 🎲 Surprise (randomize) and ↺ reset
- ⬆️ **Develop & share** — native share sheet on mobile (Save to Photos, AirDrop…), download on desktop

## Run locally

It's just one file — open `index.html` in any browser, or serve the folder:

```bash
python3 -m http.server 8123
# then visit http://localhost:8123
```

## Tech

Vanilla HTML/CSS/JS. All image processing is done with the Canvas 2D API — per-pixel color grading, radial channel-shift chroma aberration, blur-based halation, a CMYK halftone screen, and real JPEG re-encoding via `canvas.toDataURL`.

---

Built for fun. Named after the city-pop greats. 🌇
