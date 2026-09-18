# Exports & credits

## Formats

| Format | Resolution | Plan |
|---|---|---|
| **PNG — Low** | 1024 px | Free (Google sign-in) |
| **PNG — Medium** | 2048 px | Paid |
| **PNG — High** | 3200 px | Paid |
| **SVG** | Vector (resolution-independent) | Paid |
| **DXF** | Vector (CAD) | Paid |
| **GeoJSON** | Vector (georeferenced) | Paid |

### PNG

Raster output. Transparent background supported. Good for web, mockups, social, and anything where you don't need to edit the lines afterwards.

The **free tier exports a real 1024 px PNG** — sign in with a free Google account (no payment) — enough to judge the output properly, and usable as-is for plenty of work.

### SVG

Vector output: every contour is a real path. This is the format to use if you want to

- edit the lines in **Figma** or **Illustrator**
- recolour or restyle after export
- print at any size without quality loss
- drive a **laser cutter**, plotter or CNC

There's a **Flatten** option that merges all contours into a single path, so the file imports as one clean block in design tools instead of hundreds of nested groups.

### DXF (CAD)

Vector output for the CAD / fabrication world — every contour is a polyline. Import into CAD software, or send straight to a **laser cutter**, plotter or CNC toolpath. Handy when your workflow lives in DXF rather than SVG.

### GeoJSON

Georeferenced vector output for **GIS**. Contours keep their real-world coordinates, so the file lines up with other layers in QGIS, ArcGIS or a web map. You can choose the **output projection** — Web Mercator, Lambert-93, UTM and other national CRS — so the export matches your project's coordinate system.

## Credits

Paid exports run on **one-off credit packs** — there's no subscription, and **credits never expire**.

The cost of an export depends on:

- the **area** of the zone (bigger zone = more data to process)
- the **elevation resolution** (5–10 m national data costs more than the 30 m standard source)

The exact credit cost is shown before you confirm an export, and your remaining balance is always visible in the editor.

See [current packs and prices](https://www.topolines.app/#pricing).

## Resolution: standard 30 m vs national 5–10 m

- **GEDTM30 30 m** (free) — global bare-earth coverage, one sample every ~30 m. Great for most design work; the difference is invisible at poster scale for large areas.
- **National 5–10 m** (paid) — up to six times finer, from national datasets where available (IGN France 5 m, USGS 3DEP 10 m, IGN España 5 m). Worth it for small zones where you want fine detail: a single valley, an urban relief, a detailed coastline.
- **Your own DEM** (paid) — upload a GeoTIFF and trace contours on it directly, for survey data or areas the built-in sources don't cover.

## Area limits

Each zone has a maximum surface area, which is higher on paid plans. This exists to keep generation fast and reliable — very large areas produce enormous files with little visual gain.

If your zone exceeds the limit it turns red in the editor. Either shrink it, or split your subject into several zones (they can be exported together).

---

**Next:** [Figma plugin →](figma-plugin.md)
