# Greater London Railway Map — GitHub Pages

This package contains a self-contained railway-data HTML page, with Leaflet loaded from a public CDN. It does not request OpenStreetMap basemap tiles, avoiding the tile-policy block. The map still requires internet access for Leaflet JavaScript and CSS.

## Publish
1. Sign in to GitHub and create a new **public** repository, e.g. `london-railway-map`.
2. Select **Add file → Upload files**. Upload `index.html` from this ZIP (not the ZIP itself). Commit changes.
3. Open **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select **main** and **/(root)**, then Save.
4. Once published, open `https://YOUR-USERNAME.github.io/london-railway-map/`. It can take a few minutes to appear.

## Important
- This is a Phase 2 feasibility prototype based on archived Network Rail route/region geometry; not a verified current operational railway map.
- No third-party basemap is included. A licensed hosted basemap or own tiles can be added later.
- GitHub Pages is publicly accessible. Do not upload restricted employer data.
- Check licensing and attribution for all data before public publication.
