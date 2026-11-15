# FarmShift

NASA-powered crop rotation decision support. Pick a location, soil, water availability and priority; FarmShift pulls NASA POWER climate data, shows NASA GIBS satellite context and scores four rotation strategies with an explainable model.

## Run locally
Open `index.html` in a browser, or serve it: `npx serve .`

## Deploy on GitHub Pages
Push to a repo, then Settings → Pages → Deploy from branch → `main` / root.

## Data sources
NASA POWER API, NASA GIBS (MODIS), Google Maps embed, OpenStreetMap Nominatim (place search), Leaflet, Chart.js.

## Google Maps setup
1. In Google Cloud Console, enable **Maps JavaScript API** and **Geocoding API**, then create an API key.
2. Restrict the key to your site (HTTP referrers, e.g. `https://YOUR-USERNAME.github.io/*`) so it can't be misused.
3. In `index.html`, replace `PASTE_YOUR_GOOGLE_MAPS_API_KEY`. For quick local testing you can also open `index.html?gkey=YOUR_KEY`.

With a key: Google Geocoding search, an interactive Google map, and click-to-set-location. Without a key it falls back to OpenStreetMap place search and a keyless Google Maps embed.

## Forecast and Solutions
- **Forecast:** live 16-day forecast from Open-Meteo (temperature, rain, rain chance, wind and FAO-56 evapotranspiration), with a daily water-balance chart.
- **Solutions:** rule-based actions (irrigation, heat, frost, wet days, wind, soil, rotation) computed from the live forecast, NASA POWER data and the farm profile. Each card shows the numbers behind it. If the forecast cannot load, nothing is estimated.
