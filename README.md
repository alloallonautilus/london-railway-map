# Greater London Railway Map — Phase 2 v20

Consolidated research viewer for GitHub Pages. Upload **index.html**, **railway-data.js**, **exception-lines.geojson**, **route-assignment-exceptions.csv**, **clapham-endpoint-clusters.geojson**, and **clapham-tolerance-sensitivity.csv** to repository root. Keep the existing README if desired.

## Implemented
- Preserves the nine archived route polygons and four regions, 7,751 modelled track links, 5,681 network nodes and 20 approximate station markers.
- West Coast South and High Speed 1 display names; Kent teal and Wessex yellow-green.
- Route-assignment exceptions overlay (131 archived model links).
- **New:** Clapham endpoint topology overlay: 241 endpoint clusters at 2 m matching tolerance, including 63 single-endpoint clusters; interactive inspection, toggles and zoom.
- **New:** Explicit per-layer provenance and Thames disabled by default because GLA source does not cover all Greater London. The optional river layer is geographically incomplete even if every feature downloads.
- Zoom-responsive track display, search, station markers, fit-London, print and coordinate readout.

## Not achieved
- No complete Thames polygon is bundled. The partial GLA layer is optional.
- No independent individual-track data has been acquired or verified.
- No live browser test was possible in this environment.

## Sources and limitations
Organisational boundaries and track network are from archived Network Rail GIS; this is a research visualisation, not a safety-critical or authoritative current infrastructure plan. Endpoint clustering is an analytical derivative, not proof of physical junction connectivity. Do not publish restricted internal Network Rail data.
