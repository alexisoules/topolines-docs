# Cartographic options

TopoLines 2.0 adds the conventions a printed topographic sheet uses to make
contours readable. Most of them are automatic or one toggle away.

## Auxiliary contours

On flat ground — plateaus, terraces, valley floors — the standard interval can
leave large areas with no line at all. **Auxiliary contours** fill those gaps
with a dashed line at half the interval, drawn only where the terrain is
locally flat, never across slopes that already have enough lines.

- Toggle: **Auxiliary contours** in the Stroke section, **On** by default.
- Changing it re-traces the zone.
- In GeoJSON exports they carry `type: "auxiliary"`; in DXF they sit on their
  own `CONTOUR_AUXILIARY` layer, so you can hide or restyle them.

## Depression contours

A closed contour around a pit (a sinkhole, a crater, a quarry) looks exactly
like one around a hill. TopoLines detects the depressions and marks their
rings with short **hachures pointing inward**, downhill. This is automatic and
has no setting.

## Minimum contour length

Elevation models carry noise: tiny knolls and pits that trace as small closed
loops. **Min. contour length** (Settings) drops every contour shorter than the
chosen length after simplification: **None**, **20 m**, **50 m** or **100 m**.
Real terrain features are much longer than that, so they're untouched.

## Contour labels

Add **Contour labels** from the Annotations **+** menu (Pro). Elevations are
written along the contours and the line is **cut under each label**, the way a
printed map does it. The label settings let you choose text size, which contours are
labelled (label interval), spacing along the line, an optional halo stroke and
whether the `m` suffix is shown. Labels are hidden in Points mode.

## Hypsometric gradient presets (Imhof)

The gradient picker (Pro) has two presets in the style of Eduard Imhof's
hypsometric tints: lowland green through ochre and rock grey to snow white, and
a high-alpine variant that goes from dark green straight to rock and snow.
Gradients colour lines by their elevation in Lines mode, and glyphs by the
height below them in Points mode.

## Scale bar, north arrow and legend

Three toggles under the export format (PNG and SVG) add the apparatus of a
printed sheet in a **margin band below the map** — never on top of the
terrain:

- **Scale bar** — sized from the zone's real extent, metric.
- **North arrow** — the map is always north-up.
- **Legend** — in Lines mode, a line swatch for the contour interval (and the
  index interval when index contours are on). In Points mode, the smallest and
  largest glyph with the elevations they stand for.

They are drawn in the stroke colour on an opaque white band, so an export with
any of them turned on always has a solid background.

These three are **Pro**: they're baked into paid exports only. See
[Exports & plans](exports.md).

---

**Next:** [Exports & credits →](exports.md)
