# warning_viz, Antigua and Barbuda

Warning Products Portal for the UQ flood potential prototype, Antigua and Barbuda.
Developed under the WMO supported early warning activities (University of Iowa and
partners in Antigua and Barbuda, AHWA Lab).

Live site: https://ahwalab.github.io/A-B_warnings/ (repository AHWALab/A-B_warnings).
Companion products: https://ahwalab.github.io/A-B_FIM/ and https://ahwalab.github.io/A-B_IBF/.

## Files

- `index.html` landing page, Warning Products Portal
- `en.html` flood potential application, English

The application is self contained (about 11 MB) and needs the internet only for the
basemap tiles. The build scripts (steps 05 to 40) live with the training package under
`Country_trainings/A&B/web_interfaces/pipeline`.

## Enabling GitHub Pages (first time only)

1. Push this repository to GitHub (main branch).
2. On GitHub open Settings, then Pages.
3. Under Build and deployment choose Source: Deploy from a branch.
4. Select branch main and folder / (root), then Save.
5. Wait one or two minutes; the site appears at https://ahwalab.github.io/A-B_warnings/

## Basemap key

The CARTO raster basemaps (Light and Voyager) require an API key since 2026; without it the
tiles carry an "API KEY REQUIRED" watermark. The page carries the University of Iowa key in
the `CARTO_KEY` constant near the top of its script block. To change the key, edit that one
line in the built page, or in the template of the training package pipeline and rebuild.
The key is visible in the page source by design (client side tile requests); it can be
restricted to the site domain in the CARTO account settings. The OpenStreetMap and Esri
satellite basemaps do not use it.

## What it shows

Uncertainty quantified flood potential from the TITO EF5 CREST ensemble for Tropical
Storm Jerry, 9 to 11 October 2025, on the 30 m Antigua and Barbuda domain. Flood potential
classes on maximum unit streamflow in m3/s per km2, FLASH style Low to High: under 0.5 no
signal, 0.5 to 1 Low, 1 to 2 Moderate, 2 to 4 High, 4 and up Very high. Views: A, hazard
and layers; B, impact adjusted (likelihood by impact matrix with building density and
critical facilities from the Overture receptor base). Potential zones exist for all 48
cycles; the probability, potential, impact and EF5 percentile rasters are embedded for
five featured cycles and for the QPE event. Additional layers: parishes with population
and exposure counts, built-up footprint, main roads, critical facilities, gauge
hydrographs at the six EF5 output points, QPE verification, and the reported impacts of
the event. The GeoTIFF exports of the EF5 percentile fields are in the `geotiff` folder of
the training package.

This product shows flood potential. Issuing official warnings remains the mandate of the
national institutions. Prototype, not operational.

## Data and credits

TITO EF5 hindcast (StormLab 50 member forecast ensemble, STREAM-Sat 10 member QPE
ensemble). Exposure layers: Overture Maps buildings and roads, GHS BUILT-C, ADM1 parishes
with Statistics Division population estimates. Reported impacts: SIDS Flash Flood
Compendium of the project, antigua.news, NHC Tropical Cyclone Report AL102025, Antigua and
Barbuda Meteorological Service rainfall via 268weather. Basemaps: OpenStreetMap, CARTO,
Esri.
