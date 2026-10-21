# Exports & credits

## Formats

| Format | Resolution | Plan |
|---|---|---|
| **PNG — Low** | 1024 px | Free (Google or GitHub sign-in) |
| **PNG — Medium** | 2048 px | Paid |
| **PNG — High** | 3200 px | Paid |
| **SVG** | Vector (resolution-independent) | Paid |
| **DXF** | Vector (CAD) | Paid |
| **GeoJSON** | Vector (georeferenced) | Paid |

### PNG

Raster output, 1024, 2048 or 3200 px wide. Transparent background supported. Good for reports, slides, the web, and anything where you don't need to edit the lines afterwards.

The **free tier exports a real 1024 px PNG** — sign in with a free Google or GitHub account (no payment) — enough to judge the output properly, and usable as-is for plenty of work.

### SVG

Vector output: every contour is a real path. This is the format to use if you want to

- edit the lines in **Figma** or **Illustrator**
- recolour or restyle after export
- print at any size without quality loss
- drive a **laser cutter**, plotter or CNC

There's a **Flatten** option that merges all contours into a single path, so the file imports as one clean block in design tools instead of hundreds of nested groups.

### DXF (CAD)

Vector output for CAD and fabrication — every contour is a polyline, with **one layer per contour type** (index, intermediate, auxiliary, coastline), in the output CRS of your choice. Import into AutoCAD, Rhino or other CAD software for site studies, or send it to a **laser cutter**, plotter or CNC toolpath.

### GeoJSON

Georeferenced vector output for **GIS**. Contours keep their real-world coordinates, so the file lines up with other layers in QGIS, ArcGIS or a web map. Each feature carries its **elevation** and its **contour type** (`index`, `intermediate`, `auxiliary`, `coastline`).

### Output CRS (GeoJSON and DXF)

Choose the coordinate system the file is written in: WGS 84 (EPSG:4326, default), automatic UTM zone, Lambert-93 (EPSG:2154), Web Mercator (EPSG:3857), British National Grid (EPSG:27700), or ETRS89 / UTM 30N and 31N (EPSG:25830, EPSG:25831). See [Data sources](data-sources.md#coordinate-systems).

### Source metadata

PNG and vector exports embed the elevation dataset that served the zone and its licence credit, so the file documents where its contours came from.

## Credits

Paid exports run on **one-off credit packs** — there's no subscription, and **credits never expire**.

The cost of an export depends on:

- the **area** of the zone (bigger zone = more data to process)
- the **elevation resolution** (national HD data costs more than the 30 m standard source)

The exact credit cost is shown before you confirm an export, and your remaining balance is always visible in the editor.

See [current packs and prices](https://www.topolines.app/pricing).

## Resolution: standard 30 m vs national HD

- **GEDTM30 30 m** (free) — global bare-earth coverage, one sample every ~30 m. Good for regional relief and large zones.
- **National HD** (paid) — down to 1 m on small zones (0.5 m in Switzerland), coarser as the zone grows, mostly lidar-derived, in France, the US, Spain, England, Austria, Switzerland, Italy, Bavaria and North Rhine-Westphalia (see [Data sources](data-sources.md)). Worth it for small zones and site work: a single valley, a building plot, a detailed coastline.
- **Your own DEM** (paid) — upload a GeoTIFF and trace contours on it directly, for survey data or areas the built-in sources don't cover.

## Area limits

Each zone has a maximum surface area: 100 km² on the free plan, 2000 km² on paid plans (500 km² for vector exports). This keeps generation fast and reliable.

If your zone exceeds the limit it turns red in the editor. Either shrink it, or split your subject into several zones (they can be exported together).

---

**Next:** [Figma plugin →](figma-plugin.md)
