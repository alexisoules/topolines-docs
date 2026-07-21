# Data sources

TopoLines renders **real terrain**. Nothing is procedurally invented. Here's exactly where the data comes from.

## Elevation

Elevation comes from the [AWS Terrain Tiles](https://registry.opendata.aws/terrain-tiles/) open dataset, which aggregates public sources:

- **SRTM** (Shuttle Radar Topography Mission) — ~30 m resolution, near-global coverage. Used on the free tier.
- **Higher-resolution national datasets** — ~10 m where available, delivered as GeoTIFF. Used on paid tiers.

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

## Attribution & licensing

The underlying datasets are open:

- Elevation data — public domain / open data (SRTM and contributing national datasets)
- OpenStreetMap data — © OpenStreetMap contributors, [ODbL](https://www.openstreetmap.org/copyright)

**Maps you generate are yours to use**, including commercially. If you publish a map that includes OSM-derived features (coastlines, annotations), standard OpenStreetMap attribution applies — crediting "© OpenStreetMap contributors" is good practice.

See the [FAQ](faq.md) for more on commercial use.
