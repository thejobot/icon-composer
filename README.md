# Icon Composer

A zero-dependency, single-file icon design tool that runs entirely in your browser. No install, no build tools, no network calls. Double-click to open. That's it.

**[→ Launch Icon Composer](https://thejobot.github.io/icon-composer/)**

## What It Does

Design macOS-style icons by placing vector icons, text, emoji, and imported images onto shaped canvases: then export production-ready PNGs at up to 1024px.

### Canvas Shapes
- **macOS Folder**: the classic blue folder with color tinting
- **Game Boy / NES / SNES Cartridge**: retro gaming cartridge templates with full color tinting
- **Squircle / Square / Circle**: geometric shapes with gradient or solid backgrounds

### Icon Library
202 built-in stroke icons across 18 categories including Retro Gaming (gamepad, cartridge, joystick, ghost, sword, potion, chest…) and Sports (football, basketball, trophy, medal, dumbbell, jersey…), plus the full Lucide standard set for devices, code, media, files, tools, and more.

### Features
- **Drag, resize, rotate**: full spatial control with keyboard nudging
- **Per-item emboss**: debossed look with shadow/highlight/fill layers, toggled per item with type-aware offsets (tighter on text, bolder on icons)
- **Text items**: system fonts (SF Pro, SF Mono, New York), auto-scaling, full canvas item controls
- **Emoji badges**: 40 curated symbols, 6 snap positions, bitmap-correct export pipeline
- **Color tinting**: 9 preset colors + custom picker for any image-based shape
- **Custom import**: drag-drop SVG/PNG into the library
- **Multi-select**: box select or shift-click, group move/delete
- **Undo/Redo**: 30-step snapshot stack (Cmd+Z / Cmd+Shift+Z)
- **Batch export**: all 4 sizes (128/256/512/1024) in one click
- **P3 color space**: auto-detects wide-gamut displays, exports in Display P3
- **Saved sessions**: localStorage persistence

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Del` / `Backspace` | Delete selected |
| `⌘D` | Duplicate |
| `⌘Z` | Undo |
| `⌘⇧Z` | Redo |
| `↑↓←→` | Nudge 1px |
| `⇧ + Arrow` | Nudge 10px |
| `Shift + Click` | Multi-select |

## Technical Details

- **Single file**: `index.html`: all CSS, JS, icons, and images are inline
- **~130KB** total including 4 embedded base64 shape images and 202 SVG icon paths
- **Zero dependencies**: no npm, no CDN, no fonts, no network calls of any kind
- **Browser support**: Safari + Chrome on macOS (the target platform for icon design)
- **Export pipeline**: Canvas compositing with SVG data URLs (never Blob URLs), `toDataURL` download (never `toBlob`), `btoa(unescape(encodeURIComponent()))` for Unicode-safe base64 encoding
- **Text rendering**: SVG `<text>` pipeline (never `ctx.fillText`) for cross-browser baseline consistency
- **Emoji rendering**: Offscreen `ctx.fillText` at 2x resolution (emoji are bitmap font glyphs that don't render through SVG image loading on Safari)

## Running Locally

```
# Option A: just open it
open index.html

# Option B: local server (if you want)
python3 -m http.server 8000
# then visit http://localhost:8000
```

## License

MIT
