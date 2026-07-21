# Exports & credits

## Formats

| Format | Resolution | Plan |
|---|---|---|
| **PNG — Low** | 1024 px | Free, no account |
| **PNG — Medium** | 2048 px | Paid |
| **PNG — High** | 3200 px | Paid |
| **SVG** | Vector (resolution-independent) | Paid |

### PNG

Raster output. Transparent background supported. Good for web, mockups, social, and anything where you don't need to edit the lines afterwards.

The **free tier exports a real 1024 px PNG with no account** — enough to judge the output properly, and usable as-is for plenty of work.

### SVG

Vector output: every contour is a real path. This is the format to use if you want to

- edit the lines in **Figma** or **Illustrator**
- recolour or restyle after export
- print at any size without quality loss
- drive a **laser cutter**, plotter or CNC

There's a **Flatten** option that merges all contours into a single path, so the file imports as one clean block in design tools instead of hundreds of nested groups.

## Credits

Paid exports run on **one-off credit packs** — there's no subscription, and **credits never expire**.

The cost of an export depends on:

- the **area** of the zone (bigger zone = more data to process)
- the **elevation resolution** (10 m GeoTIFF costs more than 30 m SRTM)

The exact credit cost is shown before you confirm an export, and your remaining balance is always visible in the editor.

See [current packs and prices](https://www.topolines.app/#pricing).

## Resolution: SRTM 30 m vs GeoTIFF 10 m

- **SRTM 30 m** (free) — global coverage, one sample every ~30 m. Great for most design work; the difference is invisible at poster scale for large areas.
- **GeoTIFF 10 m** (paid) — three times finer. Worth it for small zones where you want fine detail: a single valley, an urban relief, a detailed coastline.

## Area limits

Each zone has a maximum surface area, which is higher on paid plans. This exists to keep generation fast and reliable — very large areas produce enormous files with little visual gain.

If your zone exceeds the limit it turns red in the editor. Either shrink it, or split your subject into several zones (they can be exported together).

---

**Next:** [Figma plugin →](figma-plugin.md)
