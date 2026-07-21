# Contour settings

Every parameter updates the render live, so the fastest way to learn them is to move a slider and watch. Here's what each one actually does.

## Contour Interval

The **vertical distance between two consecutive contour lines**, in metres (5–100 m).

A 25 m interval means every line marks a 25 m gain in altitude. Lower values = more lines = denser drawing.

| Terrain | Suggested interval |
|---|---|
| High mountains (Alps, Andes) | 50–100 m |
| Hills, mid-range relief | 20–50 m |
| Coastal, gentle terrain | 5–20 m |

If your map looks like a solid block of ink, raise the interval. If it looks empty, lower it.

## Relative Mode

**Off (default)** — the interval is absolute. 25 m means 25 m, everywhere. Two different places rendered at 25 m are directly comparable, and the line count depends on how much relief exists.

**On** — the interval adapts to the local relief so you get roughly the same *number* of lines whatever the terrain. Useful when you want a consistent visual density across a series of maps, and don't need the metres to be comparable.

> Use **Off** for anything cartographically meaningful. Use **On** when you're producing a set of posters and want them to look consistent.

## Simplification

Raw elevation data is a grid, so contours can wander along cell edges in a stair-step pattern, especially on flat terrain.

Simplification smooths that out. At `0` you get pixel-faithful lines; higher values give cleaner, more stylised curves with fewer points — which also makes the exported SVG much lighter.

> For print and laser cutting, a little simplification usually improves the result. For analysis, keep it low.

## Stroke

- **Colour** — a flat colour, or a **gradient** mapped to elevation (see below)
- **Width** — line thickness in pixels
- **Join** — how corners are drawn: `round` (softer) or `miter` (sharper)
- **Taper** — line weight varies with altitude: thicker at low elevations, thinner at the top. Gives a hand-drawn, engraved feel.

## Elevation gradient

Instead of one colour, you can map a gradient across the elevation range: stop `0%` is the lowest contour, stop `100%` the highest.

The classic hypsometric preset runs blue → green → yellow → red, which reads instantly as "low to high". Presets are available, and you can add, move and recolour stops freely.

## Annotations

Optional layers drawn in the stroke colour and included in the SVG export:

- Summits and peaks
- Rivers and water features
- Place labels
- Points of interest (mountain huts, springs, saddles)

Annotations are fetched from OpenStreetMap and only appear once contours are generated.

## Background

Flat colour, or **transparent** — useful when you want to composite the contours over your own artwork in Figma.

---

**Next:** [Exports & credits →](exports.md)
