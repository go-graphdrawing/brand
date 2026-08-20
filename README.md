<p align="center">
  <img src="https://raw.githubusercontent.com/go-graphdrawing/brand/main/png/color/256/go-graphdrawing.png" alt="go-graphdrawing" width="88" height="88">
</p>

<h1 align="center">go-graphdrawing — brand</h1>
<p align="center"><strong>The mark for the graph-drawing org — Sugiyama layering, force-directed placement, trees, planar embeddings.</strong></p>

## What is here

| Path | What it is |
|------|------------|
| `svg/go-graphdrawing.svg` | **the source of truth** — 256×256, `rx=56` rounded square, diagonal gradient, white line glyph |
| `png/color/<size>/go-graphdrawing.png` | rasterised at 16, 32, 48, 64, 88, 128, 256, 512 and 1024 px |
| `jpg/<size>/go-graphdrawing.jpg` | the same sizes, flattened onto white (JPEG has no alpha) |
| `avatar/go-graphdrawing.png` | 512 px, for the org avatar |
| `ico/go-graphdrawing.ico` | Windows icon |
| `icns/go-graphdrawing.icns` | macOS icon |
| `social/go-graphdrawing.png` | 1280x640 social preview: full-bleed gradient, glyph at 2x |

## The mark

The glyph is a node-link graph, the discipline's own picture. The gradient is the cyan of go-gfx, the 2D foundation it draws through: a family colour is shared, not invented per org.

## How the PNGs are made

By **[go-gfx/gfx](https://github.com/go-gfx/gfx)**, this fleet's own pure-Go
rasteriser, plus the standard library's PNG encoder — no Python, no Pillow, no
`sips`, no `iconutil`:

```
brandkit svg/go-graphdrawing.svg .
```

Rasterising these logos is what surfaced the gaps that
[go-gfx/gfx#12](https://github.com/go-gfx/gfx/pull/12) fixed: the rasteriser
understood fills only, so **208 of this fleet's 263 org logos came out as flat
squares** — a gradient it could not read was silently replaced by the inherited
black. Gradients, strokes and `rect rx` were added there rather than worked
around here.

The **social banner** is the mark on a full-bleed gradient with the glyph at 2x:
a preview is shown small, and a banner must never be white-backed because it is
seen against both light and dark chrome. It carries **no wordmark** — text would
need glyph outlines, and `go-opentype` keeps `glyphContours` private, so the org
name is deliberately absent rather than approximated.

## License

BSD-3-Clause, © the go-graphdrawing/brand authors.
