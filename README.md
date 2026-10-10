# v23 — bundled Thames candidate geometry

New: `thames-osm-candidates.geojson`, derived from the user-provided Overpass export containing 468 river-water polygons. A manually selected set of 23 plausible Thames sections excludes obvious tributaries. Loaded by default with no live GIS requests.

**IMPORTANT**: This is not yet a certified continuous Thames polygon. OSM polygon seams and missing western sections require further verification; do not label the layer complete. The live GLA Thames dependency is removed from the main Thames toggle.

To deploy, upload **all** files in this folder together to GitHub Pages. `index.html` alone is insufficient. The detailed infrastructure Overpass layer still uses live public requests.

Data: © OpenStreetMap contributors, ODbL. Original export supplied by user. Archived Network Rail data retains its previous caveats.
