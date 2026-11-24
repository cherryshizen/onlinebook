# onlinebook
# Leon Vasari — VHS Filmography Shelf Hero

A single-file, interactive 3D filmography hero for the fictional film director **Leon Vasari (1958–1989)**. Built with plain HTML, CSS, and vanilla JavaScript—zero frameworks, zero libraries, and no build step.

The page is styled as a warm off-white sheet of printed paper featuring an endless, tactile shelf of worn VHS tapes. Selecting any film smoothly slides the shelf and physically turns the active tape in 3D space to reveal its illustrated front cover.

---

## Features

- **Endless 3D VHS Shelf:** 12 fictional films rendered across 36 virtual 3D cuboids for seamless, infinite wrapping in both directions.
- **Physical 3D Motion:** The active tape rotates out of the shelf, tilts toward the cursor, lifts slightly, and casts a soft shadow on the paper. Dynamic face shading (`--shade`) simulates light falling across the turning cardboard box.
- **Zero Opacity Fades:** Every transition and reveal is driven by a single `requestAnimationFrame` loop and the Web Animations API—using mask slides, clips, and scales instead of CSS `@keyframes` or opacity fades.
- **Paper-Sheet Detail View:** Opening a film expands a sheet of paper directly from the active cover's 3D tilt until it fills the viewport, revealing the poster through an SVG ink-blot spread and rising each line of typography out of its own mask.
- **Custom Morphing Cursor:** A fine-pointer ring cursor that tracks with exponential smoothing, shrinks over spines and buttons, and expands into a filled cobalt `OPEN / 開く` disc over the active cover.
- **Sprite-Sheet Asset Pipeline:** All 24 spine and cover artworks are cropped dynamically from just four transparent WebP sprite sheets using calculated CSS background geometry and SVG `<clipPath>` viewports.
- **Tactile Paper Grain:** A full-screen `feTurbulence` SVG noise layer blended with `mix-blend-mode: multiply` ties the typography and 3D tapes into a unified printed-paper aesthetic.

---

## Interactions & Controls

| Input | Action |
|---|---|
| **Click Spine / Arrows** | Slide the shelf to the selected or adjacent film |
| **Decade Tabs (`1950s`–`1980s`)** | Jump to the first film of that decade with a sliding cobalt indicator |
| **Scroll / Drag** | Scrub smoothly across the endless shelf |
| **Keyboard (`←` / `→`)** | Step left or right through the filmography |
| **Click Active Cover / Play Ring / `Enter`** | Open the film's detail view |
| **Close Button / `Esc`** | Return to the shelf |

---

## Technical Highlights

- **Single-File Architecture:** Everything—markup, CSS custom properties, sprite-sheet crop coordinates, film data, and the animation engine—lives inside `index.html`.
- **Proportional Scaling:** All 3D cuboid dimensions (spine width `ws`, cover width/depth `d`, and spacing `gap`) are calculated dynamically from a single `--H` CSS token so the composition holds its proportions across desktop and mobile viewports.
- **Typography:**
  - **Newsreader** (Variable, 400 & 400 Italic) for titles, synopses, and credits.
  - **Inter Tight** (500 & 600) for uppercase boxed catalogue labels, tabs, and metadata.
  - **Noto Sans JP** (500) for Japanese titles and UI labels.
  - **Noto Serif SC** (700) for the `莱昂·瓦萨里` logotype.

---

## Getting Started

No installation or build step is required.

1. Clone or
