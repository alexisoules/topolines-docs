# FAQ

### Can I use the maps commercially?

Yes. Maps you generate are yours to use, including in client work, reports, publications and products you sell.

If your map includes OpenStreetMap-derived features (coastlines, annotations), credit "© OpenStreetMap contributors", and credit the elevation source where its licence asks for it — the credit is embedded in every export. See [Data sources](data-sources.md).

### Do I need an account to try it?

You need a free Google or GitHub sign-in — no payment. The free tier traces on GEDTM30 30 m and exports a real 1024 px PNG. Paid features (GeoJSON, DXF, SVG, HD PNG, 5–10 m data, your own DEM, larger areas) run on credits.

### Is it a subscription?

No. Credits are sold in one-off packs and **never expire**.

### How accurate is it?

Contours are only as accurate as the elevation model behind them, and TopoLines tells you which one that is. The free tier uses GEDTM30 (30 m, bare-earth); paid tiers use national terrain models at 5–10 m, mostly lidar, where available. TopoLines published a check of GEDTM30 against national lidar at eight sites: under forest its RMSE was 5–18 m, on farmland and in cities 1–5 m — see [GEDTM30 vs lidar](https://www.topolines.app/blog/gedtm30-vs-lidar).

For preliminary studies, site context and mapping it is a fast, documented source. It is **not** a substitute for a topographic survey: don't use it alone for engineering design, construction or navigation.

### Why does my map look empty / like a solid block?

Your contour interval doesn't match the terrain. Raise it on steep terrain, lower it on flat terrain. See [Contour settings](contour-settings.md).

### Why is my zone red?

It exceeds the maximum area for your plan. Shrink it, or split your subject into several zones.

### My coastline looks wrong / lines run into the sea

TopoLines clips contours against the OpenStreetMap shoreline. If that lookup fails temporarily, it falls back to a coarser method. Regenerating usually fixes it.

### Can I import my own elevation data?

Yes, on paid tiers: upload a georeferenced GeoTIFF DEM and trace contours on it directly.

### Can I edit the SVG afterwards?

Yes, that's the point. SVG exports are real vector paths that open cleanly in Figma and Illustrator. Use the **Flatten** option if you'd rather have a single merged path than grouped contours.

### Does the export include the satellite/map background?

No. Exports contain only your generated contours and annotations. The basemap is a navigation aid in the editor.

### Which projection is used?

Contours are traced in WGS 84. GeoJSON and DXF can be exported in WGS 84, an automatic UTM zone, Lambert-93, Web Mercator, British National Grid or ETRS89 UTM 30N / 31N. See [Data sources](data-sources.md#coordinate-systems).

---

Question not answered here? [Open an issue](../../issues) or see the [help page](https://www.topolines.app/help).
