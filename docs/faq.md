# FAQ

### Can I use the maps commercially?

Yes. Maps you generate are yours to use, including in client work and products you sell — posters, merchandise, brand identities, laser-cut pieces.

If your map includes OpenStreetMap-derived features (coastlines, annotations), crediting "© OpenStreetMap contributors" is good practice. See [Data sources](data-sources.md).

### Do I need an account to try it?

No. You can generate a map and download a real 1024 px PNG anonymously. An account is only needed for paid features (HD PNG, SVG, 10 m data, larger areas).

### Is it a subscription?

No. Credits are sold in one-off packs and **never expire**.

### How accurate is it?

Contours are traced from real elevation data — ~30 m sampling on the free tier, ~10 m on paid. That's accurate enough for design, visualisation and print.

It is **not** a substitute for surveyed data. Don't use it for engineering, construction or navigation.

### Why does my map look empty / like a solid block?

Your contour interval doesn't match the terrain. Raise it on steep terrain, lower it on flat terrain. See [Contour settings](contour-settings.md).

### Why is my zone red?

It exceeds the maximum area for your plan. Shrink it, or split your subject into several zones.

### My coastline looks wrong / lines run into the sea

TopoLines clips contours against the OpenStreetMap shoreline. If that lookup fails temporarily, it falls back to a coarser method. Regenerating usually fixes it.

### Can I import my own elevation data?

Not currently. Importing a custom heightmap, DEM or terrain mesh is a known request on the roadmap — [add your vote or use case](../../issues).

### Can I edit the SVG afterwards?

Yes, that's the point. SVG exports are real vector paths that open cleanly in Figma and Illustrator. Use the **Flatten** option if you'd rather have a single merged path than grouped contours.

### Does the export include the satellite/map background?

No. Exports contain only your generated contours and annotations. The basemap is a navigation aid in the editor.

### Which projection is used?

Web Mercator (EPSG:3857).

---

Question not answered here? [Open an issue](../../issues) or see the [help page](https://www.topolines.app/help).
