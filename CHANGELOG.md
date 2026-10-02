# Changelog

Notable user-facing changes to TopoLines.

## TopoLines 2.0 — October 2026

*Two readings of one terrain.*

- **Points render mode** — draw the terrain as a field of dots, squares or crosses whose density and size follow the height. Same data as the contours, one switch. Controls for density, shape, min/max size and placement (from an ordered halftone grid to a hand-stippled scatter). See [Render modes](docs/render-modes.md).
- **Printed-map conventions** — auxiliary (dashed half-interval) contours on flat ground, inward hachures on depression rings, a minimum contour length filter, and contour labels that cut the line beneath them. See [Cartographic options](docs/cartographic-options.md).
- **Scale bar, north arrow and legend** on PNG and SVG exports, drawn in a margin band below the map (Pro).
- **Annotation layers** — summits, rivers, places, contour labels, auxiliary contours and depression ticks are now layers, and each can follow the contour colour (on by default; with a gradient, depression ticks take the colour of their contour).
- **Trace preview** — open the live trace full size, on a black or white background, and export from there.
- **New basemap** — a vector map in light and dark drawn for contour work: forests, meadows, farmland, rock and ice in distinct colours, soft relief shading, and standard symbols for peaks, passes, huts, lifts and airports.
- **Smarter search** — results show what kind of place they are, and real places rank above same-named streets.
- **Off-screen zones** — a thin line on the edge of the map points to zones you've scrolled away from; click it to fly back.
- **Index contours free for everyone**, and on by default.
- **Two Imhof-style hypsometric gradient presets** (Pro).
- **Cleaner SVG for Figma** — every layer imports as a named group instead of "Group".
- **Guided tour in chapters** — Basics, Go further, What's new — plus *New* tags on new controls that disappear once used.
- **Redesigned website**, user docs and a public changelog at [topolines.app/changelog](https://www.topolines.app/changelog).
- The **Figma plugin** now draws auxiliary contours and depression hachures (Points is not in the plugin yet).

## September 2026

- **CAD & GIS vector exports** — export contours as **DXF** (for CAD, plotters and laser cutters) and **GeoJSON**, alongside SVG. GeoJSON can be written in the **output projection of your choice** (Lambert-93, UTM, and other national CRS) so it drops straight into a GIS project.
- **Bring your own DEM** — upload your own GeoTIFF raster and trace contours on it (Pro), for survey data or areas we don't cover.
- **Bare-earth elevation** — the standard worldwide source is now **GEDTM30**, which models the ground under forest canopy instead of treetops, for cleaner contours in wooded terrain.
- **National high-resolution sources** — automatic 5–10 m elevation where available: IGN RGE ALTI 5 m (France), USGS 3DEP 10 m (USA), IGN España MDT 5 m (Spain). The editor shows which source a map was traced from.
- **Search by address or coordinates** — a mode selector lets you jump to a place by name (with autocomplete), by raw coordinates, or by uploading a DEM.
- **Map info panel** — live coordinate system, scale, orientation and area of your zone, shown right in the editor.
- **Refreshed editor** — flatter, sharper interface, a precision dropdown, a dark basemap by default, and a scan-line effect while contours generate.
- **Faster generation** — traces are cached per zone and inland areas skip the coastline lookup, so restyling and revisiting a place is near-instant.
- **Privacy self-service** — export or erase your account data yourself, no email required (GDPR).

## July 2026

- **Topographic map directory** — browse generated contour maps for 90+ cities and micro-states at [topolines.app/topographic-map](https://www.topolines.app/topographic-map), each opening directly in the editor.
- **Clearer export tiers** — PNG resolution is now driven by the format tier: Low 1024 px (free), Medium 2048 px, High 3200 px, plus vector SVG.
- **Relative mode** — keep a consistent number of contour lines across places with very different relief.
- **Elevation gradients & taper** — colour and line weight can now follow altitude.

## June 2026

- **Annotations** — optional summits, rivers, place labels and points of interest, included in SVG exports.
- **Real coastline clipping** — contours are cut against OpenStreetMap shorelines instead of noisy radar data.

---

Have an idea? [Open a feature request](../../issues/new?template=feature_request.md).
