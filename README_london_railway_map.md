# London Railway Map

Interactive map of the **archived Network Rail Regions and Routes intersecting Greater London**, with modelled railway centrelines, a station-location layer and a River Thames overlay.

**Live map:** https://alloallonautilus.github.io/london-railway-map/  
**Repository:** https://github.com/alloallonautilus/london-railway-map

> **Scope and caution:** This is a geographical reference and research map, **not an authoritative statement of current Network Rail Route responsibility**. Its Network Rail organisational geography comes from an archived public dataset. A railway feature's position within a Route polygon does not by itself establish which organisation manages or maintains it.

## Contents

| Layer | Bundled contents | Interpretation |
|---|---:|---|
| Network Rail Routes | 9 polygons | Archived Route geography, with display names adapted where noted |
| Network Rail Regions | 4 polygons | Archived Region geography |
| Railway network | 7,751 centreline links | Modelled links, **not** surveyed individual running tracks |
| Network nodes | 5,681 points | Nodes in the modelled railway network |
| Station locations | 339 markers | Representative positions derived from NaPTAN railway-entrance records |
| River Thames | 42 OSM-derived candidate polygons | Contextual river geometry; coverage not independently certified |
| Greater London boundary | 1 boundary layer | Geographic study area |

The optional detailed railway infrastructure view requests OpenStreetMap features through the Overpass API when enabled. Its content and availability depend on OSM coverage, the current viewport and external service availability; it is **not** a complete bundled infrastructure inventory.

## Station names and symbols

- Major central London termini use larger white circular symbols with a dark centre dot. Other stations use smaller white circular symbols.
- Permanent station-name labels begin at **zoom level 13** for **all** stations, including major termini.
- Labels use collision-aware, alternative-position placement to reduce overlap. Major termini are prioritised; labels may be withheld when insufficient space is available.
- Station markers remain visible even when their permanent labels are suppressed. Hovering reveals the station name.
- “Major terminus” is a **cartographic category**, not a claim about Network Rail managed-station status.

## Data sources and provenance

1. **Archived Network Rail GIS** — public Route polygons, Region polygons and modelled railway-network geometry. Repository: https://github.com/openraildata/network-rail-gis . The archived baseline is not verified as current.
2. **Greater London Authority (GLA)** — Greater London administrative boundary. Public GLA ArcGIS contextual geography: https://gis.london.gov.uk/arcgis/rest/services/apps/webmap_context_layer/MapServer/1 .
3. **Department for Transport, NaPTAN** — user-supplied London-area export `490Stops.csv` (area code `082`), used to build `station-data.js`. Download portal: https://beta-naptan.dft.gov.uk/download . The source contained **549 active RSE (railway station entrance) records**, consolidated into **339 distinct station-name markers**. Each marker represents a station name using its entrance-coordinate positions, not a surveyed station centroid. Some categories may differ from the ORR's National Rail station inventory.
4. **© OpenStreetMap contributors** — OSM-derived Thames water polygons bundled as `thames-osm-candidates.geojson`; and optional detailed railway infrastructure requested live using Overpass. Attribution/licence: https://www.openstreetmap.org/copyright . Overpass API information: https://wiki.openstreetmap.org/wiki/Overpass_API .

The map's displayed Route names and colours are presentation choices. In particular, **High Speed 1 is distinct from conventional Network Rail Routes and has separate infrastructure-management arrangements**. Do not infer current asset-level responsibility from the colour of a polygon.

### Route colours

| Display label | Colour |
|---|---|
| Anglia | `#2C7FB8` |
| East Coast | `#800000` |
| East Midlands | `#8E6BB1` |
| High Speed 1 | `#7DF9FF` |
| Kent | `#004225` |
| Sussex | `#EFA638` |
| Wessex | `#A6C83A` |
| Western | `#CC144E` |
| West Coast South | `#30343F` |

## Verification and limitations

Checks performed during development included geometry-validity tests on the bundled Route, Region, railway-link and Thames layers; reconciliation of the 339 station names against the supplied NaPTAN export; and checks that station coordinates fall inside Greater London and near modelled railway centrelines.

These checks support **internal consistency**, but do not independently establish:
- That archived Route boundaries match today's Network Rail organisational responsibilities.
- That all current National Rail stations within Greater London are represented.
- That every railway link, individual track or asset is present or accurately attributed.
- That the 42 bundled Thames polygons provide complete river coverage.
- That live Overpass queries always return complete results.

This application should not be used to make operational, safety-critical or contractual determinations of railway infrastructure responsibility.

## Running and publishing

This is a static web application hosted on GitHub Pages. Keep **all five files in the repository root**:

```text
index.html
railway-data.js
station-data.js
thames-osm-candidates.geojson
README.md
```

To deploy, commit the files to the `main` branch and enable **Settings → Pages → Deploy from a branch → main → / (root)**. The HTML loads its JavaScript datasets locally and fetches the Thames GeoJSON by relative path. Leaflet assets are loaded from a CDN; the optional infrastructure view also needs access to Overpass.

No Clapham-specific audit files or controls are required.

## Related project

The separate **London Railway Infrastructure Responsibility Map** explores geographically inferred Route assignments and unresolved interfaces. Its analytical classifications should not be confused with the archived geographical reference presented here.
