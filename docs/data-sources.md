# Data sources

TopoLines renders **real terrain**. Nothing is procedurally invented. Here's exactly where the data comes from.

## Elevation

TopoLines picks the best available elevation source for your area:

- **GEDTM30** — a global **bare-earth** model at ~30 m, which represents the ground surface under forest canopy rather than treetops. This is the standard, free source worldwide.
- **National high-resolution datasets** — ~5–10 m where available, used on paid tiers: **IGN RGE ALTI 5 m** (France), **USGS 3DEP 10 m** (USA), **IGN España MDT 5 m** (Spain), with more added over time. The editor's Map info panel shows which source a map was traced from.
- **Your own GeoTIFF** — on paid tiers you can upload your own DEM and trace contours on it directly, for survey data or areas the built-in sources don't cover.

Contour lines are traced from that elevation grid at the interval you choose.

## Coastlines

Sea and shoreline geometry comes from [OpenStreetMap](https://www.openstreetmap.org/) (`natural=coastline`).

This matters more than it sounds: radar-derived elevation data is noisy near the shore, so tracing contours straight from the DEM puts the 0 m line hundreds of metres out to sea. TopoLines clips contours against the real OSM shoreline instead, so lines stop exactly where the land does.

## Annotations

Summits, rivers, place labels and points of interest are queried from OpenStreetMap.

## Basemap

The map you navigate in the editor uses standard map and satellite tile providers. **Basemap imagery is never part of your export** — exports contain only the generated contours (and annotations, if enabled).

## Projection

Contours are generated and rendered in **Web Mercator (EPSG:3857)**, the standard web mapping projection — so exports align with any other web map layer you might composite them with.

**GeoJSON exports can be reprojected** to the coordinate system of your choice — Lambert-93, UTM zones and other national CRS — so the file drops straight into a GIS project without a reprojection step.

## Attribution & licensing

The underlying datasets are open:

- Elevation data — open data (GEDTM30 and contributing national datasets)
- OpenStreetMap data — © OpenStreetMap contributors, [ODbL](https://www.openstreetmap.org/copyright)

**Maps you generate are yours to use**, including commercially. If you publish a map that includes OSM-derived features (coastlines, annotations), standard OpenStreetMap attribution applies — crediting "© OpenStreetMap contributors" is good practice.

See the [FAQ](faq.md) for more on commercial use.
