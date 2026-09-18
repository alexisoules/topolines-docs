# Changelog

Notable user-facing changes to TopoLines.

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
