# Open national elevation models (DTM): access notes

A practical list of **open, programmatically accessible digital terrain models** — what each one is, its licence, and how to actually read it over HTTP without downloading a whole country. Every entry below is wired into TopoLines and was tested against the live service; the quirks column is what we learned doing it.

Machine-readable version: [`data/national-elevation-models.csv`](../data/national-elevation-models.csv). Last verified: October 2026.

## Worldwide

| Dataset | Publisher | Native resolution | Type | Licence | Access |
|---|---|---|---|---|---|
| **GEDTM30 v1.2** | OpenGeoHub | 30 m | Bare-earth DTM (ML ensemble) | CC BY 4.0 | One global Cloud-Optimized GeoTIFF on [OpenTopography](https://opentopography.s3.sdsc.edu/raster/GEDTM30/GEDTM30_be/) (mirror: OpenGeoHub S3) |
| **Terrain Tiles** | Mapzen / Nextzen, AWS Open Data | ~10 m at z13 (varies by source) | Composite (SRTM, national DEMs) | Open data, per-source attribution | GeoTIFF tiles `s3.amazonaws.com/elevation-tiles-prod/geotiff/{z}/{x}/{y}.tif` |

- GEDTM30 is bare earth: under forest it follows the ground, not the canopy. Reference: Ho, Hengl et al. (2025), *PeerJ*, [doi:10.7717/peerj.19673](https://doi.org/10.7717/peerj.19673). How it compares with national lidar at eight sites: [GEDTM30 vs lidar](https://www.topolines.app/blog/gedtm30-vs-lidar).
- Terrain Tiles carry positive, noisy heights over the sea near the shore — clip with a coastline (e.g. OpenStreetMap `natural=coastline`) before tracing a 0 m contour.

## National models

| Coverage | Dataset | Publisher | Native resolution | Type | Licence | Access | Native CRS |
|---|---|---|---|---|---|---|---|
| Metropolitan France | **RGE ALTI®** | IGN | 1 m (5 m also published) | Lidar + photogrammetry | Etalab 2.0 | [WMS](https://data.geopf.fr/wms-r/wms), float32 GetMap | EPSG:2154 |
| United States | **3DEP** | USGS | 1 m / 1/9″ lidar where flown, 1/3″ (~10 m) elsewhere | Lidar + legacy DEMs | Public domain | [ImageServer](https://elevation.nationalmap.gov/arcgis/rest/services/3DEPElevation/ImageServer) `exportImage` | Mosaic |
| Spain | **MDT05** | IGN España | 5 m (MDT02 also published) | Lidar (PNOA) | CC BY 4.0 | [WCS 2.0.1](https://servicios.idee.es/wcs-inspire/mdt) | EPSG:4258 |
| England | **LIDAR Composite DTM 2022** | Environment Agency | 1 m | Lidar | OGL v3.0 | [WCS](https://environment.data.gov.uk/spatialdata/lidar-composite-digital-terrain-model-dtm-1m-2022/wcs) | EPSG:27700 |
| Switzerland | **swissALTI3D** | swisstopo | 0.5 m / 2 m | Lidar | Open data (attribution) | [STAC API](https://data.geo.admin.ch/api/stac/v0.9/collections/ch.swisstopo.swissalti3d/items) → 1 km COG tiles | EPSG:2056 |
| Austria | **ALS DTM Österreich** | BEV | 1 m | Lidar | CC BY 4.0 | [50 km COG tiles](https://data.bev.gv.at/download/ALS/DTM/20250915) | EPSG:3035 |
| Italy | **TINITALY/1.1** | INGV | 10 m | Mixed (contours, spot heights, GPS, lidar) | CC BY 4.0 | [WCS](https://tinitaly.pi.ingv.it/TINItaly_1_1/wcs) | EPSG:32632 |
| Germany – NRW | **DGM1** | Geobasis NRW | 1 m | Lidar | dl-de/zero-2.0 | [WCS 2.0.1](https://www.wcs.nrw.de/geobasis/wcs_nw_dgm) | EPSG:25832 |
| Germany – Bavaria | **DGM1** | Bayerische Vermessungsverwaltung | 1 m | Lidar | CC BY 4.0 | [1 km GeoTIFF tiles](https://download1.bayernwolke.de/a/dgm/dgm1) | EPSG:25832 |

## Access quirks worth knowing

- **France (IGN)** — the Géoplateforme WMS returns raw float32 elevations, not a shaded image, for `ELEVATION.ELEVATIONGRIDCOVERAGE.HIGHRES` (the 1 m RGE ALTI). One GetMap answers a whole bounding box; no key. Measured October 2026: 3.5 Mpx answers in 1–6 s at 1, 2 or 5 m; a 4.2 Mpx request resampled to 5 m returned 504.
- **United States (USGS 3DEP)** — the ImageServer mosaic picks the best available source per pixel, so a 1–5 m request returns lidar-derived heights where flown and the 1/3″ product elsewhere. Sea and areas outside coverage come back as nodata.
- **Spain (IGN)** — coverage `Elevacion4258_5`. There is no void value: the sea and land outside Spain both come back as a flat 0, so mask them before tracing.
- **England (EA)** — the WCS only behaves in its native CRS. Subset in eastings/northings with `SCALEFACTOR` (1 for the native 1 m; 0.2 gives 5 m for a 6 × 6 km box in about a second); lon/lat subsets error or hang.
- **Switzerland (swisstopo)** — several survey years can exist for one tile; keep the newest. Tiles are kilometre-aligned, so they mosaic without resampling.
- **Austria (BEV)** — 55 published tiles in EPSG:3035 with internal overviews: windowed reads at 5–20 m only pull a few MB. Nodata is −9999.
- **Italy (INGV)** — served in UTM 32N for the whole country, eastern regions included.
- **Germany** — there is no free nationwide DGM1 (the BKG's is licensed); each Land publishes its own. Bavaria has no open WCS (the INSPIRE one needs a login), only 1 km GeoTIFF tiles of ~2.5 MB that are not cloud-optimized. Baden-Württemberg's INSPIRE WCS answers, but over part of the Land returns whole-metre integers with no CRS, which terraces contours.

## Licences in one line each

CC BY 4.0, OGL v3.0, Etalab 2.0 and swisstopo open data require attribution; USGS 3DEP is public domain; dl-de/zero-2.0 requires none. TopoLines writes the required credit into the metadata of every export.

## Corrections and additions

Know an open national DTM with a usable web service that isn't here, or spotted an error? [Open an issue](https://github.com/alexisoules/topolines-docs/issues/new?template=feature_request.md).
