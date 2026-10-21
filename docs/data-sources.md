# Data sources

TopoLines traces **real terrain** from documented, citable datasets. Nothing is procedurally invented. Every trace states which dataset served the zone — in the editor's Map info panel and in the metadata of every export.

## Elevation

| Dataset | Publisher | Resolution | Coverage | Licence |
|---|---|---|---|---|
| GEDTM30 v1.2 (bare-earth DTM) | OpenGeoHub, via OpenTopography | 30 m | Worldwide | CC BY 4.0 |
| Terrain Tiles (GeoTIFF) | Mapzen / Nextzen, AWS Open Data | ~10 m | Worldwide | Open data |
| RGE ALTI® | IGN | 1–5 m | Metropolitan France | Etalab 2.0 |
| 3DEP | U.S. Geological Survey | Up to 1 m | United States | Public domain |
| swissALTI3D | swisstopo | 0.5–10 m | Switzerland | Open data (attribution) |
| LIDAR Composite DTM | Environment Agency | 1–20 m | England | OGL v3.0 |
| MDT | Instituto Geográfico Nacional | 5 m | Spain | CC BY 4.0 |
| ALS DTM Österreich | BEV | 1–20 m | Austria | CC BY 4.0 |
| TINITALY/1.1 | INGV | 10–30 m | Italy | CC BY 4.0 |
| DGM1 | Bayerische Vermessungsverwaltung, Geobasis NRW | 1–20 m | Bavaria, North Rhine-Westphalia | CC BY 4.0 / dl-de/zero-2.0 |

- **GEDTM30** is the free, worldwide default. It is a **bare-earth** model: it represents the ground under forest canopy rather than treetops. Reference: Ho, Hengl et al. (2025), *PeerJ*, [doi:10.7717/peerj.19673](https://doi.org/10.7717/peerj.19673).
- **National models** (Pro) are mostly lidar-derived terrain models. USGS 3DEP is served on a 1, 2 or 5 m grid from 1 m or 1/9″ lidar where it has been flown, and from the ~10 m 1/3″ product elsewhere — hence "up to".
- **Your own GeoTIFF** (Pro) — upload a georeferenced DEM and trace contours on it directly, for survey data or areas the built-in sources don't cover.

### Automatic precision

A national model is served at the **finest grid the zone allows**, never finer than the model itself. Contour tracing time grows with the number of grid cells, so every HD trace gets the same budget of about 3.5 million cells:

| Grid | Largest zone (approx.) |
|---|---|
| 0.5 m | 0.9 km² (Switzerland only) |
| 1 m | 3.5 km² |
| 2 m | 14 km² |
| 5 m | 85 km² |
| 10 m | 350 km² |
| 15 m | 790 km² |
| 20 m | 1,400 km² |
| 30 m | 3,000 km² (Italy only) |

Each model starts at its native grid (0.5 m Switzerland; 1 m France, England, Austria, Germany, US; 5 m Spain; 10 m Italy). Areas are for a roughly square zone; a long, thin one moves to the next grid sooner. The grid used is part of the source label, e.g. "IGN RGE ALTI 2 m".

### How a source is chosen

- A national model is used only when the zone lies **entirely inside its coverage**. A zone crossing a border uses the worldwide source, so a map is never stitched from two datasets.
- Large zones inside one country depend on the model: England, Austria, Italy, Switzerland and the German states **coarsen their grid** (up to 10–30 m) to stay on national data; France, Spain and the United States stay national **up to about 85 km²** (France: 1 m up to ~3.5 km², 2 m up to ~14 km², then 5 m) and fall back to the worldwide 10 m source beyond that.
- The editor shows the source and grid your zone will get **before** you generate.

Full table with credits: [topolines.app/docs/datasets](https://www.topolines.app/docs/datasets).

## Coastlines

Sea and shoreline geometry comes from [OpenStreetMap](https://www.openstreetmap.org/) (`natural=coastline`), queried through the Overpass API.

This matters more than it sounds: many elevation models report non-zero heights over water, so tracing contours straight from the DEM puts the 0 m line out at sea. TopoLines clips contours against the OSM shoreline and masks the sea, so lines stop where the land does.

## Annotations

Summits, rivers, place labels and points of interest (huts, springs, saddles) are queried from OpenStreetMap.

## Basemap

The map you navigate in the editor is an OpenStreetMap-based vector basemap ([OpenFreeMap](https://openfreemap.org/)), with a satellite view; place search uses Nominatim. **Basemap imagery is never part of your export** — exports contain only the generated contours (and annotations, if enabled).

## Coordinate systems

Contours are traced in **WGS 84 (EPSG:4326)**. GeoJSON and DXF exports can be reprojected on the way out:

| Option | EPSG |
|---|---|
| WGS 84 (default) | 4326 |
| UTM, zone picked automatically from the zone centre | 326xx / 327xx |
| RGF93 / Lambert-93 | 2154 |
| Web Mercator | 3857 |
| OSGB36 / British National Grid | 27700 |
| ETRS89 / UTM 30N, 31N | 25830, 25831 |

## Attribution & licensing

- Elevation data — see the licence column above. The required credit for the dataset that served your zone is embedded in every export.
- OpenStreetMap data — © OpenStreetMap contributors, [ODbL](https://www.openstreetmap.org/copyright)

**Maps you generate are yours to use**, including commercially. If you publish a map that includes OSM-derived features (coastlines, annotations), credit "© OpenStreetMap contributors", and credit the elevation source where its licence asks for it (CC BY, OGL, Etalab).

See the [FAQ](faq.md) for more on commercial use.
